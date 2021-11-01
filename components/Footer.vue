<template>
  <footer class="footer" :class="!isDarkTheme ? 'text-dark bg-light' : ''">
    <div class="container-lg">
      <template v-if="isDarkTheme">
        <img
          src="../static/blklight-white.svg"
          title="Ultimate Mercer"
          width="50"
          class="mx-auto d-block"
        />
      </template>
      <template v-else>
        <img
          src="../static/blklight-black.svg"
          title="Ultimate Mercer"
          width="50"
          class="mx-auto d-block"
        />
      </template>
    </div>
  </footer>
</template>
<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters(["isDarkTheme"]),
  },
};
</script>
