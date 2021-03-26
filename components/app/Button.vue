<template>
  <button text>
    <a :href="url" target="blank">
      {{ text }}
    </a>
  </button>
</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: '',
    },
    text: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
button {
  @apply p-1;
  @apply border-2;
  @apply border-gray-300;
  @apply rounded-lg;
  @apply bg-gray-200;
}
a {
  @apply no-underline;
}
</style>
