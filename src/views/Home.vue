<template>
  <div class="home">
    <Header />
    <main><Nav /><Articles /></main>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Nav from "@/components/Nav.vue";
import Articles from "@/components/Articles.vue";

export default {
  name: "Home",
  components: {
    Header,
    Footer,
    Nav,
    Articles,
  },
  created() {
    this.$store.dispatch("initData");
  },
};
</script>
