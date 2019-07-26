<template>
  <header class="header">
    <nav class="nav">
      <h1 class="text text__nav">
        <g-link to="/" class="link">Blog</g-link>
      </h1>
      <ToggleTheme />
      <h1 class="text text__nav">
        <g-link to="/me" class="link">Me</g-link>
      </h1>
    </nav>
  </header>
</template>

<style lang="postcss">
.header {
  position: fixed;
  z-index: 2;
  display: flex;
  width: 100%;
  height: 60px;
  background-color: var(--primary-backround-color);
}
.nav {
  display: flex;
  width: 100%;
  height: 100%;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}
.text__nav {
  margin: 0;
  font-family: var(--base-font);
  font-size: 1.5rem;
}
</style>

<script>
import ToggleTheme from "~/components/ToggleTheme.vue";

export default {
  components: {
    ToggleTheme
  }
};
</script>

