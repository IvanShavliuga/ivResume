<template>
  <header>
    <div class="contacts">
      <ol>
        <li>
          <p>{{ profile.geo }}</p>
        </li>

        <li>
          <p>
            <a :href="profile.github" rel="noopener" :title="profile.github">
              github.com {{ profile.github }}</a
            >
          </p>

          <p>
            <a :href="profile.email" rel="noopener" :title="profile.email">
              {{ profile.email }}
            </a>
          </p>
        </li>

        <li>
          <p title="The user wanted to hide their phone number">
            {{ profile.phone }}
          </p>
          <p>The user wanted to hide their phone number</p>
        </li>
      </ol>
    </div>
    <div class="name">
      <div class="userdata">
        <div class="photouser"></div>
        <h1>{{ profile.name }}</h1>
        <p>{{ profile.prof }}</p>
        <p>
          <span>
            <router-link to="/ru" rel="noopener" class="link">
              RU
            </router-link></span
          >
          <span>
            |
            <router-link to="/en" rel="noopener" class="link"> EN</router-link>
          </span>
        </p>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      profile: {},
    };
  },
  created() {
    // this.$store.dispatch("initData");
    this.profile = this.$store.getters.profile;
  },
};
</script>
