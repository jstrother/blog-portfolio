<template>
  <div class="share-twitter">
    <div class="call-to-tweet">
      Share this article with the world!
      <br />
      Let everyone know you think this is a great read!
    </div>
    <a
      href="https://twitter.com/share?ref_src=twsrc%5Etfw"
      class="twitter-share-button"
      :data-text="description"
      :data-url="`https://www.jimstrother.com/blog/${urlTitle(title)}`"
      data-via="Jim_Codes_JS"
      :data-hashtags="`${hashtag}`"
      data-show-count="false"
      >Tweet</a
    >
    <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    hashtag: {
      type: String,
      required: true,
    },
  },
  methods: {
    urlTitle(string) {
      return string.trim().replace(/\s+/g, '-').toLowerCase();
    },
  },
};
</script>

<style scoped>
.share-twitter {
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply justify-center;
  @apply items-center;
}
.call-to-tweet {
  @apply text-center;
}
</style>
