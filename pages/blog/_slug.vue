<template>
  <article>
    <Title
      :title="article.title"
      :description="article.description"
      :img="article.img"
      :alt="article.alt"
      :updated="formatDate(article.updatedAt)"
    />
    <Nav :toc="article.toc" />
    <nuxt-content :document="article" />
    <SimpleLine />
    <div class="post-footer">
      <ShareTwitter
        :title="article.title"
        :description="article.description"
        :hashtag="article.hashtag"
      />
      <TipMe />
    </div>
    <PrevNext :prev="prev" :next="next" />
  </article>
</template>

<script>
import Title from '~/components/blog/post/Title';
import Nav from '~/components/blog/post/Nav';
import ShareTwitter from '~/components/blog/post/ShareTwitter';
import TipMe from '~/components/blog/post/TipMe';
import PrevNext from '~/components/blog/post/PrevNext';
import SimpleLine from '~/components/app/SimpleLine';

export default {
  components: {
    Title,
    Nav,
    ShareTwitter,
    TipMe,
    PrevNext,
    SimpleLine,
  },
  async asyncData({ $content, params }) {
    const article = await $content('articles', params.slug).fetch();

    const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch();

    return { article, prev, next };
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' };
      return new Date(date).toLocaleDateString('en', options);
    },
  },
};
</script>

<style scoped>
article {
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply my-14;
  @apply mx-auto;
  @apply w-9/12;
}
.post-footer {
  @apply flex;
  @apply flex-row;
  @apply flex-wrap;
  @apply justify-around;
}
</style>
