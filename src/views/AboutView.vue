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
  <div class="about-container">
    <div class="about">
      <IconLogoEventHorizonFullENUS class="logo-full" />
      <p>
        尽所能将星际公民世界的魅力展现给每个人。我们是一个制作各种游戏内视频和微电影的制作组，希望你能喜欢。<br />
        Trying our best to present the beauty and charm of Star Citizen World to everyone. We
        produce many kinds of in-game short films and videos. Hope you like them.
      </p>
      <p class="social">
        Find us on
        <a href="https://space.bilibili.com/3546685305260617" target="_blank" rel="noopener"
          >bilibili</a
        >
        |
        <a href="https://www.youtube.com/@EventHorizon_PG" target="_blank" rel="noopener"
          >YouTube</a
        >
      </p>
    </div>
    <div class="member-list">
      <MemberInfo
        v-for="member in newMemberList"
        :name="member.name"
        :name_zh="member.name_zh"
        :game_id="member.game_id"
        :title="member.title_zh"
        :links="member.links"
      />
    </div>
  </div>
</template>

<style scoped>
.about-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  position: absolute;
  padding: 0 1rem;
}
.about {
  padding-top: 30vh;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: start;
}
.logo-full {
  height: 8rem;
  margin-bottom: 1rem;
  max-width: 100%;
}
.about > p {
  line-height: 2;
  color: var(--color-text-soft);
}
.member-list {
  padding-top: 2rem;
  padding-bottom: 4rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  overflow: visible;
}

@media (min-width: 1024px) {
  .about-container {
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }
  .member-list {
    padding-top: 30vh;
    overflow: scroll;
  }
}
</style>
