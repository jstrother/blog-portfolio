<template>
  <main>
    <section class="title-bar">
      <h1>Blog Posts</h1>
      <ArticleSearch />
    </section>
    <section class="posts">
      <div v-for="(article, index) of articles" :key="index">
        <nuxt-link class="link" :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <ArticleCard
            :img="article.img"
            :alt="article.alt"
            :title="article.title"
            :author="article.author.name"
            :created-at="formatDate(article.createdAt)"
            :description="article.description"
          />
        </nuxt-link>
      </div>
    </section>
  </main>
</template>

<script>
import ArticleSearch from '~/components/blog/ArticleSearch';
import ArticleCard from '~/components/blog/ArticleCard';

export default {
  components: {
    ArticleSearch,
    ArticleCard,
  },
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug)
      .only(['title', 'description', 'img', 'alt', 'slug', 'author', 'createdAt'])
      .sortBy('createdAt', 'desc')
      .fetch();

    return { articles };
  },
  methods: {
    formatDate(date) {
      return new Date(date).toLocaleDateString('en', {
        year: 'numeric',
        month: 'long',
        day: 'numeric',
      });
    },
  },
};
</script>

<style scoped>
main {
  @apply flex-grow flex flex-col flex-nowrap mb-auto p-14 bg-gray-200;
}
.title-bar {
  @apply justify-self-start flex flex-nowrap justify-around content-center;
}
h1 {
  @apply text-2xl font-bold pt-2.5;
}
.posts {
  @apply flex justify-around;
}
</style>
