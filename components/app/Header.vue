<template>
  <header>
    <nuxt-link class="header-link" to="/">Jim Strother</nuxt-link>
    <div class="flex-1"></div>
    <Navigation class="flex-initial" />
  </header>
</template>

<script>
import Navigation from '~/components/app/Navigation';
export default {
  components: {
    Navigation,
  },
};
</script>

<style scoped>
header {
  @apply min-w-full h-14 bg-gray-500 flex fixed z-50;
}
.header-link {
  @apply text-white no-underline flex-initial flex justify-center items-center m-4;
}
.nuxt-link-exact-active {
  @apply text-gray-900 text-lg;
}
</style>
