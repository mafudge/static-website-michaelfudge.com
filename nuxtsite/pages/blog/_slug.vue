<script>
export default {
  async asyncData({ $content, params }) {
    // fetch our article here
    const article = await $content("articles", params.slug).fetch();
    return { article };
  },
  methods: {
    imageUrl(image) {
      return `/${image}`;
    },
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
};
</script>

<style>
h1,
.nuxt-content h1 {
  font-weight: bold;
  font-size: 28px;
}
h2,
.nuxt-content h2 {
  font-weight: bold;
  font-size: 24px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content p {
  margin-bottom: 20px;
}
.icon.icon-link {
  background-image: url("~assets/svg/icon-hashtag.svg");
  display: inline-block;
  width: 20px;
  height: 20px;
  background-size: 20px 20px;
}
</style>


<template>
  <article>
    <h1>{{ article.title }}</h1>
    <p>
      Article last updated: {{ formatDate(article.updatedAt) }} by
      {{ article.author.name }}
    </p>
    <img :src="require(`~/assets/${article.img}`)" :alt="article.alt" />
    <h1>Contents</h1>
    <nav>
      <ul>
        <li v-for="link of article.toc" :key="link.id">
          <NuxtLink :to="`#${link.id}`" :class="{ 'py-2': link.depth === 2, 'ml-2 pb-2': link.depth === 3 }">{{ link.text }}</NuxtLink>
        </li>
      </ul>
    </nav>
    <hr>
    <nuxt-content :document="article" />
    <author :author="article.author"/>
    <hr>
    <h1>DEBUG:</h1>
    <pre> {{ article }} </pre>
  </article>
</template>