<template>
  <div class="search">
    <input v-model="searchQuery" type="search" autocomplete="off" placeholder="Search Articles" />
    <div v-if="articleList.length">
      <br />
      <ul>
        <li v-for="(article, index) of articleList" :key="index">
          <nuxt-link class="link" :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            {{ article.title }}
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: '',
      articleList: [],
    };
  },
  watch: {
    async searchQuery(query) {
      if (!query) {
        this.articleList = [];
      }

      this.articleList = await this.$content('articles')
        .limit(7)
        .search('title', query)
        .sortBy('title', 'asc')
        .fetch();
    },
  },
};
</script>

<style scoped>
.search {
  @apply self-center;
  @apply border;
  @apply border-black;
  @apply rounded-lg;
  @apply p-2;
  @apply my-2;
  @apply -mr-4;
}
input {
  @apply text-center;
  @apply outline-none;
}

ul {
  @apply list-none;
}

.link {
  @apply no-underline;
  @apply text-black;
}
</style>
