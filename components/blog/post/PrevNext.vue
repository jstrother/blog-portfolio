<template>
  <div class="prevNext">
    <nuxt-link v-if="prev" class="link" :to="{ name: 'blog-slug', params: { slug: prev.slug } }">
      <img src="/img/icons/chevron-left.png" alt="Previous Article" />
      <span class="prevSpan">{{ prev.title }}</span>
    </nuxt-link>
    <span v-else>&nbsp;</span>
    <nuxt-link v-if="next" class="link" :to="{ name: 'blog-slug', params: { slug: next.slug } }">
      <span class="nextSpan">{{ next.title }}</span>
      <img src="/img/icons/chevron-right.png" alt="Next Articl" />
    </nuxt-link>
    <span v-else>&nbsp;</span>
  </div>
</template>

<script>
export default {
  props: {
    prev: {
      type: Object,
      default: () => null,
    },
    next: {
      type: Object,
      default: () => null,
    },
  },
};
</script>

<style scoped>
.prevNext {
  @apply flex justify-between pt-4;
}
.link {
  @apply flex no-underline;
}
span {
  @apply mt-2;
}
.prevSpan {
  @apply -ml-3;
}
.nextSpan {
  @apply -mr-3;
}
img {
  @apply -mt-0.5;
}
</style>
