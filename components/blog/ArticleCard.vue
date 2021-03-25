<template>
  <div class="card">
    <img :src="img" :alt="alt" />
    <h3 class="title">{{ title }}</h3>
    <h4 class="subtitle">
      <span>{{ author }}</span>
      <span>{{ createdAt }}</span>
    </h4>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    img: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    author: {
      type: String,
      required: true,
    },
    createdAt: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  @apply flex;
  @apply flex-col;
  @apply flex-wrap;
  @apply m-2;
  @apply rounded-lg;
  @apply shadow-lg;
  @apply bg-gray-50;
}
img {
  @apply max-w-full;
  @apply max-h-20;
  @apply rounded-t-lg;
}
.title {
  @apply self-center;
  @apply text-xl;
  @apply font-medium;
}
.subtitle {
  @apply flex;
  @apply flex-row;
  @apply flex-nowrap;
  @apply justify-around;
  @apply font-light;
}
p {
  @apply p-2;
  @apply font-light;
}
</style>
