<script setup>
import { RouterLink, RouterView } from 'vue-router'
import IconLogoEventHorizon from './components/icons/IconLogoEventHorizon.vue'
</script>

<template>
  <header>
    <div class="backdrop"></div>
    <RouterLink to="/"><IconLogoEventHorizon class="logo" /></RouterLink>
    <div class="grow"></div>

    <nav>
      <RouterLink to="/works">作品</RouterLink>
      <!-- <RouterLink to="/feeds">Feeds</RouterLink> -->
      <RouterLink to="/about">关于</RouterLink>
    </nav>
  </header>
  <div class="main">
    <RouterView />
  </div>
</template>

<style scoped>
header {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  line-height: 1.5;
  color: var(--color-text);
  padding: 1rem;
  font-family: var(--font-geom);
  z-index: 100;
}

.backdrop {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  mask-image: linear-gradient(black 20%, transparent);
  backdrop-filter: blur(4px);
}

header > * {
  flex-shrink: 0;
}

header > a {
  color: inherit;
  background-color: transparent;
  padding: 0;
  display: block;
  display: flex;
  align-items: center;
}

header > a:hover {
  opacity: 0.75;
}
header a::after {
  display: none;
}

.logo {
  width: 3rem;
}

.grow {
  flex-grow: 1;
}

nav {
  flex-shrink: 0;
  font-size: 1rem;
  text-align: center;
}

nav a {
  display: inline-block;
  padding: 0.5rem 1rem;
  color: var(--color-text);
  text-transform: uppercase;
}

nav a.router-link-exact-active {
  color: var(--color-text-soft);
  cursor: default;
}

nav a.router-link-exact-active:hover {
  color: var(--color-text-soft);
  background-color: transparent;
}

nav a:hover {
  color: var(--color-background);
  background-color: var(--color-text);
}

.main {
  padding-top: 3.875rem;
}

@media (min-width: 1024px) {
  header {
    padding: 2rem;
  }

  .main {
    padding-top: 4.875rem;
  }
}
</style>
