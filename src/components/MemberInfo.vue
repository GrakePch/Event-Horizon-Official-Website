<script setup>
import { defineProps } from 'vue'
import avatarDefault from '@/assets/avatars/_default.png'
import avatars from '@/assets/avatars/avatars.js'

const props = defineProps({
  name: String,
  name_zh: String,
  game_id: String,
  title: String,
  avatar: String,
  links: Array
})
</script>

<template>
  <div class="member">
    <img :src="avatars[name] || avatarDefault" class="avatar" />
    <div class="member-text">
      <h2>
        {{ props.name_zh || props.name }}
        <span v-if="props.game_id"
          ><a
            :href="'https://robertsspaceindustries.com/citizens/' + props.game_id"
            target="_blank"
            rel="noopener"
            >@{{ props.game_id }}</a
          ></span
        >
      </h2>
      <h3>
        <template v-for="t in props.title.split(' / ')"
          ><span>{{ t }}</span></template
        >
      </h3>
      <p>
        <template v-for="[index, [text, href]] in links?.entries()">
          <template v-if="index > 0"> | </template>
          <a :href target="_blank" rel="noopener">{{ text }}</a>
        </template>
      </p>
    </div>
  </div>
</template>

<style scoped>
.member {
  display: flex;
  gap: 1rem;
  line-height: 1.5;
}
.avatar {
  width: 5rem;
  height: 5rem;
}
.member-text {
  font-family: var(--font-geom);
}

.member-text h2 {
  line-height: 1;
  font-weight: bold;
  align-items: center;
  display: flex;
  gap: 0.25ch;
}
.member-text h2 span {
  color: var(--color-text-soft);
  font-family: var(--font-sans);
  font-size: 1rem;
}
.member-text h2 span > a {
  color: inherit;
}
.member-text h2 span > a:hover {
  opacity: 0.75;
}
.member-text h2 span > a::after {
  display: none;
}
.member-text h3 {
  /* text-transform: uppercase; */
  display: flex;
  flex-wrap: wrap;
  gap: 0.25rem;
  margin-top: 0.5rem;
  margin-bottom: 0.25rem;
}
.member-text h3 > span {
  color: var(--color-background);
  background-color: var(--color-text-soft);
  font-size: 0.875rem;
  font-family: var(--font-sans);
  font-weight: 600;
  padding: 0 0.25rem;
}

.member-text p {
  color: var(--color-text-soft);
  font-family: var(--font-sans);
}
</style>
