<script setup lang="ts">
import IconLogoEventHorizonFullENUS from '@/components/icons/IconLogoEventHorizonFullENUS.vue'
import MemberInfo from '@/components/MemberInfo.vue'
import members from '@/assets/data/members.json'
let founders = members.slice(0, 3)
let shuffled = members
  .slice(3)
  .map((value) => ({ value, sort: Math.random() }))
  .sort((a, b) => a.sort - b.sort)
  .map(({ value }) => value)
let newMemberList = founders.concat(shuffled)
</script>

<template>
  <div class="about">
    <IconLogoEventHorizonFullENUS class="logo-full" />
    <p>
      尽所能将星际公民世界的魅力展现给每个人。我们是一个制作各种游戏内视频和微电影的制作组，希望你能喜欢。<br />
      Trying our best to present the beauty and charm of Star Citizen World to everyone. We produce
      many kinds of in-game short films and videos. Hope you like them.
    </p>
    <p class="social">
      Find us on
      <a href="https://space.bilibili.com/3546685305260617" target="_blank" rel="noopener"
        >bilibili</a
      >
      |
      <a href="https://www.youtube.com/@EventHorizon_PG" target="_blank" rel="noopener">YouTube</a>
    </p>
  </div>
  <div class="member-list">
    <MemberInfo
      v-for="member in newMemberList"
      :name="member.name"
      :game_id="member.game_id"
      :title="member.title_zh"
      :links="member.links"
    />
  </div>
</template>

<style scoped>
.about {
  padding-top: 15vh;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: start;
}
.logo-full {
  height: 8rem;
  margin-bottom: 1rem;
}
.about > p {
  line-height: 2;
  color: var(--color-text-soft);
}
.member-list {
  padding-top: 15vh;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

@media (min-width: 1200px) {
  .about {
    position: fixed;
    width: calc(50% - 4rem);
  }
  .member-list {
    padding-left: calc(50% + 2rem);
  }
}
</style>
