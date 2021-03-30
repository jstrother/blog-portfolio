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
  @apply flex flex-col h-screen min-w-full justify-between;
}
</style>
