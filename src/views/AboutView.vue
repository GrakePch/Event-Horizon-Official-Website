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
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porta rutrum risus, nec placerat
      metus auctor ut. Nulla vel vehicula mauris, sed semper risus. Maecenas blandit convallis
      sapien ut tempus. Aenean ac tristique nisl. Vivamus blandit risus ut dolor tincidunt, sit amet
      facilisis neque auctor. Maecenas dignissim nisl eget risus eleifend commodo. In nec nibh
      commodo, hendrerit sem at, semper nisl. Vivamus faucibus sodales risus at posuere.
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
