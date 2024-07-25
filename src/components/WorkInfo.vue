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
      <div class="id-and-date">
        <small class="id">事件视界作品 #{{ props.id }}</small>
        <small class="date">{{ `${props.date[0]}-${props.date[1]}-${props.date[2]}` }}</small>
      </div>
      <h1>{{ props.title }}</h1>
      <p v-if="props.watch.bilibili && props.watch.YouTube" class="watch-links">
        Watch on <a :href="props.watch.bilibili" target="_blank" rel="noopener">bilibili</a> |
        <a :href="props.watch.YouTube" target="_blank" rel="noopener">YouTube</a>
      </p>
      <p v-else-if="props.watch.bilibili" class="watch-links">
        Watch on <a :href="props.watch.bilibili" target="_blank" rel="noopener">bilibili</a>
      </p>
      <p v-else-if="props.watch.YouTube" class="watch-links">
        Watch on <a :href="props.watch.bilibili" target="_blank" rel="noopener">YouTube</a>
      </p>
      <template v-else />

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
.id-and-date {
  display: flex;
  align-items: center;
  gap: 1ch;
}
.id {
  display: block;
  color: var(--color-background);
  background-color: var(--color-text);
  font-size: 1.25rem;
  font-weight: bold;
  font-family: var(--font-geom);
  line-height: 1.5;
  text-transform: uppercase;
  font-variant-numeric: tabular-nums;
  padding: 0 0.5ch;
}
.date {
  font-size: 1.25rem;
  color: var(--color-text-soft);
  font-family: var(--font-geom);
  line-height: 1;
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
