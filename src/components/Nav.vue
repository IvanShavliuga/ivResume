<template>
  <nav>
    <ul class="menulist">
      <li class="item">
        <h2>Profile</h2>
        <div class="desc">
          h3 {{ profile.name }}
          <p>
            <b> {{ profile.prof }}</b>
          </p>
          <p>I make site layout to order.</p>
          <p>
            <a :href="profile.email" rel="noopener">
              {{ profile.email }}</a>
          </p>
          <p><router-link to="/" rel="noopener"> Home page</router-link></p>
          <p><router-link to="/List" rel="noopener"> My posts</router-link></p>
          <p>
            <router-link to="/Portfolio" rel="noopener">
              My portfolio</router-link
            >
          </p>
        </div>
      </li>
      <li class="item">
        <h2>Interests</h2>
        <div class="images">
          <div class="interes"><p>Podcast</p></div>
          <div class="interes"><p>Books</p></div>
          <div class="interes"><p>Design</p></div>
        </div>
      </li>
      <li class="item">
        <h2>Skills</h2>
        <div class="desc">
          <ul class="skills">
            <li v-for="s in profile.skills" :key="s">{{ s }}</li>
          </ul>
        </div>
      </li>
      <li class="item">
        <h2>Education</h2>
        <div class="desc">
          <ul>
            <li class="line" v-for="(e, k) in edu" :key="k">
              <div class="lineinfo">
                {{ e.years }}
                <a :href="e.link" target="_blank" rel="noopener">
                  {{ e.caption }}</a
                >
                <span> {{ e.desc }}</span>
              </div>
            </li>
          </ul>
        </div>
      </li>
      <li class="item">
        <h2>Work experience</h2>
        <div class="desc">
          <ul>
            <li class="line" v-for="(w, k) in works" :key="k">
              <div class="lineinfo">
                {{ w.years }}
                <a :href="w.link" target="_blank" rel="noopener">
                  {{ w.caption }}</a
                >
                <span> {{ w.desc }}</span>
              </div>
            </li>
          </ul>
        </div>
      </li>
    </ul>
  </nav>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  computed: {
    ...mapGetters(["profile", "works", "portfolio", "edu"]),
  },
};
</script>
