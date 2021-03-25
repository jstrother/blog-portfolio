<template>
  <div class="container">
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/app/Header';
import Footer from '~/components/app/Footer';
export default {
  components: {
    Header,
    Footer,
  },
};
</script>

<style scoped>
.container {
  @apply flex;
  @apply flex-col;
  @apply h-screen;
  @apply min-w-full;
  @apply justify-between;
}
</style>
