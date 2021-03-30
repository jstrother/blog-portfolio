<template>
  <footer>
    <a v-for="item in contact" :key="item.index" class="m-4" :href="item.link" target="_blank">
      <img :src="item.icon" :alt="item.name" />
    </a>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      contact: [
        {
          icon: '/img/icons/github.png',
          link: 'https://github.com/jstrother',
          name: 'GitHub Logo',
        },
        {
          icon: '/img/icons/twitter.png',
          link: 'https://twitter.com/Jim_Codes_JS',
          name: 'Twitter Logo',
        },
        {
          icon: '/img/icons/linkedin.png',
          link: 'https://www.linkedin.com/in/jimstrother/',
          name: 'LinkedIn Logo',
        },
      ],
    };
  },
};
</script>

<style scoped>
footer {
  @apply min-w-full h-14 bg-gray-300 flex justify-center items-center bottom-0;
}
</style>
