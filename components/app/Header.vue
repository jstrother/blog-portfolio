<template>
  <div class="header">
    <nuxt-link class="header-link" to="/">Jim Strother</nuxt-link>
    <div class="flex-1"></div>
    <Navigation class="flex-initial" />
  </div>
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
.header {
  @apply min-w-full;
  @apply bg-gray-500;
  @apply flex;
}
.header-link {
  @apply text-white;
  @apply no-underline;
  @apply flex-initial;
  @apply flex;
  @apply justify-center;
  @apply items-center;
  @apply m-4;
}
</style>
