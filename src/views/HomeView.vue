<script setup>
import coverImage from '@/assets/img/cover-4.bmp'
</script>

<template>
  <main>
    <div class="highlight-cover" :style="{ backgroundImage: `url(${coverImage})` }"></div>
    <div class="highlight-text-anchor">
      <section class="highlight-text">
        <small>访谈纪录片</small>
        <h1>你为什么喜欢星际公民？</h1>
        <p>
          星际公民为每个人都带来了亦充满美好亦留有遗憾的回忆。但最重要的是，每一份回忆都是独属于自己的那份精彩。无论你之前是否有思考过这个问题，当你直面它的时候，你会给出什么答案呢？
        </p>
        <p class="watch-links">
          前往观看：<a
            href="https://www.bilibili.com/video/BV1QPhzeaEw6"
            target="_blank"
            rel="noopener"
            >bilibili</a
          >
          | <a href="https://youtu.be/GO6HACwqLos" target="_blank" rel="noopener">YouTube</a>
        </p>
      </section>
    </div>
  </main>
</template>

<style scoped>
.highlight-cover {
  aspect-ratio: 21 / 9;
  color: var(--color-text-soft);
  background-size: cover;
  background-repeat: no-repeat;
  overflow: hidden;
}

.highlight-text-anchor {
  position: relative;
}

.highlight-text {
  position: absolute;
  top: 2rem;
  left: 0;
  color: #fff;
  line-height: 1.25;
  width: 100%;
  max-width: 58rem;
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
  margin: 0.5rem 0;
}
.highlight-text > p {
  font-size: 1rem;
}
.watch-links {
  margin-top: 1rem;
}
@media (min-width: 1200px) {
  .highlight-text {
    top: auto;
    bottom: 0;
    padding: 4rem;
  }
}
</style>
