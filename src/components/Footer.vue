<template>
  <footer>
    <ul class="social">
      <li v-for="(s, k) in social" :key="social + k">
        <a :href="s.link" target="_blank" :id="s.name + '_' + k" rel="noopener">
          {{ s.name }}</a
        >
      </li>
    </ul>
    <div class="copyright">
      <p>
        &copy; 2020 {{ profile.geo }}, {{ profile.name }}, {{ profile.prof }}
      </p>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      profile: {},
      social: {},
    };
  },
  created() {
    // this.$store.dispatch("initData");
    this.profile = this.$store.getters.profile;
    this.social = this.$store.getters.links;
  },
};
</script>
