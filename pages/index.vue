<template>
  <LayoutContent>
    <main class="d-flex flex-column justify-content-center py-3">
      <h1 class="font-monospace text-center text-uppercase">Deploys</h1>
    </main>
    <section class="container-lg">
      <h2
        class="mb-4"
        :class="
          isDarkTheme
            ? 'text-light cyber-underline-light'
            : 'text-dark cyber-underline-dark'
        "
      >
        <em>Últimas artigos</em>
      </h2>
      <CardHorizontal
        v-for="article in articles"
        :key="article.slug"
        :article="article"
      />
    </section>
  </LayoutContent>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  async asyncData({ $content, params }) {
    const articles = await $content("articles", { deep: true }, params.slug)
      .only([
        "title",
        "abstract",
        "imageHeader",
        "cover",
        "slug",
        "dir",
        "channel",
        "category",
        "createdDate",
        "featured",
        "type",
        "author",
        "isPublished",
      ])
      .sortBy("createdDate", "desc")
      .where({
        type: "normal",
        isPublished: true,
        channel: { $ne: "Jobs" },
      })
      .fetch();
    return { articles };
  },

  computed: {
    ...mapGetters(["isDarkTheme"]),
  },
};
</script>
