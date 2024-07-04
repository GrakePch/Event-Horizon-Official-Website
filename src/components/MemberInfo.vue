<script setup>
import { defineProps } from 'vue'
import avatarDefault from '@/assets/avatars/_default.png'
import avatars from '@/assets/avatars/avatars.js'

const props = defineProps({
  name: String,
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
        {{ props.name }}
        <span
          ><a
            :href="'https://robertsspaceindustries.com/citizens/' + props.game_id"
            target="_blank"
            rel="noopener"
            >@{{ props.game_id }}</a
          ></span
        >
      </h2>
      <h3>{{ props.title }}</h3>
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
  text-transform: uppercase;
}

.member-text p {
  color: var(--color-text-soft);
  font-family: var(--font-sans);
}
</style>
