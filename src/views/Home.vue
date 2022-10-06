<template>
  <div class="home">
    <Header />
    <main><Nav /></main>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Nav from "@/components/Nav.vue";

export default {
  name: "Home",
  components: {
    Header,
    Footer,
    Nav,
  },
  created() {
    this.$store.dispatch("initData");
  },
};
</script>
