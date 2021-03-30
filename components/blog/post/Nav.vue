<template>
  <nav>
    <SimpleLine />
    <h2>Content</h2>
    <ul>
      <li v-for="(link, index) of toc" :key="index">
        <nuxt-link :class="{ 'sub-heading': link.depth === 3 }" :to="`#${link.id}`">
          {{ link.text }}
        </nuxt-link>
      </li>
    </ul>
    <SimpleLine />
  </nav>
</template>

<script>
import SimpleLine from '~/components/app/SimpleLine';

export default {
  components: {
    SimpleLine,
  },
  props: {
    toc: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
ul {
  @apply pl-4 list-none;
}
.sub-heading {
  @apply pl-4;
}
</style>
