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
  @apply flex flex-col flex-wrap m-2 rounded-lg shadow-lg bg-gray-50;
}
img {
  @apply max-w-full max-h-20 rounded-t-lg;
}
.title {
  @apply self-center text-xl font-medium;
}
.subtitle {
  @apply flex flex-row flex-nowrap justify-around font-light;
}
p {
  @apply p-2 font-light;
}
</style>
