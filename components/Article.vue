<template>
  <section class="main-article mb-5">
    <ArticleHeader :article="headerData" />
    <article class="mb-5" :class="[!isDarkTheme ? 'light-theme' : '']">
      <nuxt-content :document="article" class="mono-font" />
    </article>
  </section>
</template>
<script>
import { mapGetters } from "vuex";

export default {
  props: {
    article: {
      type: Object,
      default: null,
    },
  },

  computed: {
    ...mapGetters(["isDarkTheme"]),
    headerData() {
      return {
        title: this.article.title,
        date: this.article.createdDate,
        abstract: this.article.abstract,
        category: this.article.category,
        channel: this.article.channel,
        // tags: this.article.attributes.tags,
        cover: this.article.cover,
        imageHeader: this.article.imageHeader,
        headerLayout: this.article.headerLayout,
      };
    },
  },
};
</script>
<style lang="scss">
.gallery-block {
  display: grid;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.25rem;

  &-content {
    display: inline-block;
    margin: 1rem 1rem;
  }

  &-img {
    max-width: 100%;
    height: 600px;
    object-fit: cover;
  }
}

@media screen and (max-width: 768px) {
  .gallery-block {
    display: grid;
    max-width: 100%;
    margin: 0 auto;
    padding: 0 1rem;

    &-content {
      display: block;
      margin: 1rem 1rem;
    }

    &-img {
      max-width: 100%;
      height: 500px;
      object-fit: cover;
      margin: 0 auto;
      display: block;
    }
  }
}

// .nuxt-content {
//   border: 1px solid #480bff;
// }
</style>
