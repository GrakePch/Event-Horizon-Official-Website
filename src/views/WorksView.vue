<script setup>
import works from '@/assets/data/works.json'
import WorkInfo from '@/components/WorkInfo.vue'
</script>

<template>
  <div>
    <WorkInfo
      v-for="work in works"
      :title="work.title"
      :description="work.description"
      :id="work.id"
      :watch="work.watch"
    />
  </div>
</template>
