<script setup>
import covers from '@/assets/img/covers'
import { defineProps } from 'vue'

const props = defineProps({
  title: String,
  description: String,
  id: Number,
  watch: Object
})
</script>

<template>
  <section class="work">
    <img :src="covers[props.id]" class="cover" />
    <div class="work-text">
      <small>Event Horizon Work #{{ props.id }}</small>
      <h1>{{ props.title }}</h1>
      <p class="watch-links">
        Watch on <a :href="props.watch.bilibili" target="_blank" rel="noopener">bilibili</a> |
        <a :href="props.watch.YouTube" target="_blank" rel="noopener">YouTube</a>
      </p>
      <p class="description">{{ props.description }}</p>
    </div>
  </section>
</template>
<style scoped>
.work {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}
.cover {
  width: 100%;
}
.work-text > small {
  font-size: 1.5rem;
  color: var(--color-text-soft);
  font-weight: 500;
  font-family: var(--font-geom);
  line-height: 100%;
  text-transform: uppercase;
  letter-spacing: -0.1ch;
  word-spacing: 0.25ch;
}
.work-text > h1 {
  font-size: 3rem;
  font-weight: bold;
  font-family: var(--font-geom);
  line-height: 125%;
}
.watch-links {
  line-height: 4;
}
.description {
  line-height: 2;
  color: var(--color-text-soft);
}

@media (min-width: 1024px) {
  .work {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
