<script setup>
import works from '@/assets/data/works.json'
import WorkInfo from '@/components/WorkInfo.vue'
</script>

<template>
  <div class="works-list">
    <WorkInfo
      v-for="work in works.sort((a, b) => b.id - a.id)"
      :title="work.title"
      :description="work.description"
      :id="work.id"
      :watch="work.watch"
    />
  </div>
</template>

<style scoped>
.works-list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
</style>
