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
  @apply flex;
  @apply flex-col;
  @apply justify-center;
  @apply items-center;
  @apply pt-2;
  @apply mb-2;
}
h1 {
  @apply text-5xl;
  @apply mb-2;
}
img {
  @apply max-w-xs;
  @apply max-h-60;
  @apply rounded-md;
}
</style>
