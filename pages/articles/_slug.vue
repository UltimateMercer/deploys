<template>
  <LayoutContent>
    <Article :article="article" />
  </LayoutContent>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug).fetch();

    return { article };
  },
};
</script>

<style lang="scss">
.header-post {
  width: 100%;
  height: 600px;
  object-fit: cover;
  margin: 0 0 1rem 0;
  // border-radius: 0.5rem;
}
</style>
