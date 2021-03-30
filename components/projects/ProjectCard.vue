<template>
  <div class="card">
    <section class="card-title">
      <h3 class="title">{{ name }}</h3>
      <img :src="image" :alt="`${name} Image`" :title="name" />
    </section>
    <p>{{ description }}</p>
    <section class="btn-container">
      <Button v-show="gitHub" :url="gitHub" text="GitHub" />
      <Button v-show="liveExample" :url="liveExample" text="Live Example" />
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
      default: '',
    },
    liveExample: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped>
.card {
  @apply flex flex-col flex-wrap justify-between m-2 p-2 rounded-lg shadow-lg w-96 bg-gray-50;
}
.card-title {
  @apply flex flex-col flex-nowrap items-center md:flex-row justify-around;
}
h3 {
  @apply font-medium mb-2;
}
img {
  @apply w-48 max-w-full rounded-xl mb-2;
}
.btn-container {
  @apply flex justify-around m-2;
}
</style>
