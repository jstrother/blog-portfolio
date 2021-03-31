<template>
  <div class="title">
    <h1>{{ title }}</h1>
    <p>{{ description }}</p>
    <p>written by Jim Strother</p>
    <h6>Last Updated: {{ updated }}</h6>
    <img :src="img" :alt="alt" :title="alt" />
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    updated: {
      type: String,
      required: true,
    },
    img: {
      type: String,
      default: '',
    },
    alt: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped>
.title {
  @apply flex flex-col justify-center items-center pt-2 mb-2;
}
h1 {
  @apply text-3xl md:text-4xl mb-2;
}
img {
  @apply max-w-xs max-h-60 rounded-md;
}
</style>
