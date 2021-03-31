<template>
  <div class="flex">
    <div v-for="(item, index) in navList" :key="index" class="m-4 self-end">
      <nuxt-link class="nav-link" :to="`/${item.link}`">{{ item.title }}</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navList: [
        {
          title: 'Skills',
          link: 'skills',
        },
        {
          title: 'Projects',
          link: 'projects',
        },
        {
          title: 'Blog',
          link: 'blog',
        },
      ],
    };
  },
};
</script>

<style scoped>
.nav-link {
  @apply text-white no-underline;
}
.nuxt-link-exact-active {
  @apply text-gray-900 text-lg;
}
</style>
