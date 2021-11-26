<script>
export default {
  props: {
    author: {
      type: Object,
      required: true,
    },
  },
};
</script>


<template>
  <div class="p-4 mb-4 text-white bg-blue-500">
    <h4>About {{ author.name }}</h4>
    <img :src="author.image" />
    <p>{{ author.bio }}</p>
  </div>
</template>