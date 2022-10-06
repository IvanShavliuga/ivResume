<template>
  <section>
    <h2>Portfolio</h2>
    <div class="works">
      <article v-for="(p, k) in portfolio" :key="k" :id="'article-' + k">
        <h3>{{ p.title }}</h3>
        <a :href="p.sitelink" rel="noopener" target="_blank">
          {{ p.sitetitle }}</a
        >

        <p>{{ p.desc }}</p>
        <ul class="skills">
          <li
            v-for="(t, k1) in p.tech"
            :key="k + '_' + k1"
            :id="'tech-' + k1 + '_' + k1"
          >
            {{ t }}
          </li>
        </ul>
      </article>
    </div>
    <h2>Creation</h2>
    <ul class="creative">
      <li
        v-for="(c, k) in creative"
        :key="'creative_' + k"
        :id="'creative_' + k"
      >
        <h3>{{ c.category }}</h3>
        <p
          v-for="(l, k1) in c.linkslist"
          :key="'creative_' + k1 + '_' + k"
          :id="'creative_' + k + '_' + k1"
        >
          <a :href="l.link" target="_blank" rel="noopener" :title="l.name">
            {{ l.name }}</a
          >
        </p>
      </li>
    </ul>
  </section>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  computed: {
    ...mapGetters(["profile", "works", "portfolio", "edu"]),
  },
};
</script>
