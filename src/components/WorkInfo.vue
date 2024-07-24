<script setup>
import covers from '@/assets/img/covers'
import { defineProps } from 'vue'
import bg_lines from '@/assets/lines.png'

const props = defineProps({
  title: String,
  description: String,
  id: Number,
  date: [Number, Number, Number],
  watch: Object
})
</script>

<template>
  <section class="work">
    <img v-if="covers[props.id]" class="cover" :src="covers[props.id]" />
    <div v-else class="cover no-cover" :style="{ 'background-image': 'url(' + bg_lines + ')' }">
      <p>暂无封面</p>
    </div>
    <div class="work-text">
      <small
        >事件视界作品 #{{ props.id }} |
        {{ `${props.date[0]} - ${props.date[1]} - ${props.date[2]}` }}</small
      >
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
.cover.no-cover {
  display: flex;
  align-items: center;
  justify-content: center;
  aspect-ratio: 16 / 9;
  opacity: 0.25;
  background-position: center;
  background-size: 4rem;
}
.cover.no-cover > p {
  background-color: #000;
  padding: 1.5rem 3rem;
  font-size: 1.5rem;
}
.work-text {
  display: flex;
  flex-direction: column;
  gap: 1rem;
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
  font-variant-numeric: tabular-nums;
}
.work-text > h1 {
  font-size: 3rem;
  font-weight: bold;
  font-family: var(--font-geom);
  line-height: 125%;
}
.watch-links {
  line-height: 2;
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
