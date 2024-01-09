<template>
  <section class="hero is-dark is-fullheight-with-navbar">
    <div class="hero-body">
      <div class="container has-text-centered">
        <hr class="border-line has-background-white" />
        <div class="title">{{ profile ? profile.greeting : '' }}</div>
        <div class="subtitle">
          {{ profile ? profile.intro : '' }}
        </div>
        <hr class="border-line min has-background-white" />
      </div>
    </div>
  </section>
</template>

<script>
import { getProfile } from '@/repositories/profile';

export default {
  name: 'About',
  data() {
    return {
      profile: {}
    };
  },
  mounted() {
    this.profile = getProfile();
  }
};
</script>

<style scoped>
.hero {
  align-items: center;
}
.hero .hero-body {
  max-width: 600px;
}
.container .border-line {
  height: 3px;
  margin-bottom: 20px;
  width: 100%;
}
.container .title {
  margin-bottom: 40px;
}
.border-line.min {
  width: 100px;
  margin: 0 auto 20px auto;
}
.social-links {
  display: flex;
  justify-content: center;
  gap: 12px;
}
.social-links a,
a:hover,
a:focus,
a:active {
  text-decoration: none;
  color: inherit;
}
</style>
