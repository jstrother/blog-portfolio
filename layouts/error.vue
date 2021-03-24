<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">
      {{ pageNotFound }}
    </h1>
    <h1 v-else>
      {{ otherError }}
    </h1>
    <p>
      <span v-if="error.statusCode === 404">Somehow you found a page I didn't create!</span>
      <span v-else>Wow. I'm not sure at all what happened here.</span>
      <br />
      Click below to head back to the main page.
      <br />
      <br />
    </p>
    <NuxtLink to="/" class="home"> Home page </NuxtLink>
  </div>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred',
    };
  },
  head() {
    const title = this.error.statusCode === 404 ? this.pageNotFound : this.otherError;
    return {
      title,
    };
  },
};
</script>

<style scoped>
.container {
  @apply flex;
  @apply flex-col;
  @apply justify-center;
  @apply items-center;
}
h1 {
  @apply text-lg;
}
.home {
  @apply underline;
}
</style>
