<script setup>
import coverImage from '@/assets/img/cover-4.bmp'
</script>

<template>
  <main>
    <div class="highlight-cover" :style="{ backgroundImage: `url(${coverImage})` }">
      <div>
        <section class="highlight-text">
          <small>访谈纪录片</small>
          <h1>你为什么喜欢星际公民？</h1>
          <p>
            星际公民为每个人都带来了亦充满美好亦留有遗憾的回忆。但最重要的是，每一份回忆都是独属于自己的那份精彩。无论你之前是否有思考过这个问题，当你直面它的时候，你会给出什么答案呢？
          </p>
        </section>
      </div>
    </div>
  </main>
</template>

<style scoped>
.highlight-cover {
  aspect-ratio: 21 / 9;
  background-color: #80808040;
  background-size: cover;
  background-repeat: no-repeat;
  padding: 4rem;
  overflow: hidden;
}

.highlight-cover > div {
  position: relative;
  width: 100%;
  height: 100%;
}

.highlight-text {
  position: absolute;
  bottom: 0;
  left: 0;
  color: #fff;
  line-height: 1.25;
  width: 50%;
  max-width: 50rem;
  /* background-color: #fffdfe;
  box-shadow: 0 0 5rem 5rem #fffdfe; */
}
.highlight-text > small {
  font-size: 2rem;
  font-weight: normal;
  color: #ffffff80;
  font-family: var(--font-geom);
}
.highlight-text > h1 {
  font-size: 4rem;
  font-weight: bold;
  font-family: var(--font-geom);
}
.highlight-text > p {
  font-size: 1rem;
}
</style>
