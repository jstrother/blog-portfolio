<template>
  <div class="card">
    <section class="card-title">
      <h3 class="title">{{ name }}</h3>
      <img :src="image" :alt="`${name} Image`" :title="name" />
    </section>
    <p>{{ description }}</p>
    <section class="btn-container">
      <Button :url="gitHub" text="GitHub Repository" />
      <Button :url="liveExample" text="Live Example" />
    </section>
  </div>
</template>

<script>
import Button from '~/components/app/Button';

export default {
  components: {
    Button,
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    gitHub: {
      type: String,
      required: true,
    },
    liveExample: {
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
  @apply p-2;
  @apply rounded-lg;
  @apply shadow-lg;
  @apply w-96;
  @apply bg-gray-50;
}
.card-title {
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply items-center;
  @apply md:flex-row;
  @apply justify-around;
}
img {
  @apply w-48;
  @apply max-w-full;
  @apply rounded-xl;
}
.btn-container {
  @apply flex;
  @apply justify-around;
  @apply m-2;
}
</style>
