<template>
  <div class="border-bottom border-2 border-primary">
    <header class="header container py-5 py-lg-13 d-lg-flex fw-bold">
      <ul
        class="d-none justify-content-between flex-grow-1 me-12 me-xl-23 d-lg-flex font-jost fs-5 nav-font"
      >
        <li><RouterLink to="/">About Me</RouterLink></li>
        <li>
          <RouterLink to="/">Last Activity</RouterLink>
        </li>
        <li><RouterLink to="/">Policy</RouterLink></li>
        <li><IconLogo class="position-relative icon-logo"></IconLogo></li>
        <li><RouterLink to="/">Donate</RouterLink></li>
        <li><RouterLink to="/">Feedback</RouterLink></li>
      </ul>

      <ul class="d-none d-lg-flex gap-6 ms-auto">
        <li>
          <a href="#"><IconFB /></a>
        </li>
        <li>
          <a href="#"><IconIG /></a>
        </li>
        <li>
          <a href="#"><IconYT /></a>
        </li>
        <li>
          <a href="#"><IconLine /></a>
        </li>
      </ul>

      <div class="d-lg-none text-primary lh-1">
        <span @click="menuToggle" v-show="!menuIsShow" class="material-symbols-outlined">
          menu
        </span>
        <span @click="menuToggle" v-show="menuIsShow" class="material-symbols-outlined">
          close
        </span>
        <IconLogo class="position-absolute start-50 translate-middle z-30 icon-logo"></IconLogo>
      </div>
    </header>
    <div :class="{ 'h-0': !menuIsShow }" class="px-8 bg-white z-20 menu">
      <ul class="font-jost md:fs-5 mt-100px text-center fw-bold">
        <li class="mb-13"><RouterLink to="/" class="d-block">About Me</RouterLink></li>
        <li class="mb-13">
          <RouterLink to="/" class="d-block">Last Activity</RouterLink>
        </li>
        <li class="mb-13"><RouterLink to="/">Policy</RouterLink></li>

        <li class="mb-13"><RouterLink to="/" class="d-block">Donate</RouterLink></li>
        <li class="mb-13"><RouterLink to="/" class="d-block">Feedback</RouterLink></li>
      </ul>
      <ul class="pt-13 pb-30 border-top gap-4 d-flex justify-content-center">
        <li>
          <a href="#" class="rounded-circle p-5 border"><IconFB /></a>
        </li>
        <li>
          <a href="#" class="rounded-circle p-5 border"><IconIG /></a>
        </li>
        <li>
          <a href="#" class="rounded-circle p-5 border"><IconYT /></a>
        </li>
        <li>
          <a href="#" class="rounded-circle p-5 border"><IconLine /></a>
        </li>
      </ul>
    </div>
  </div>
  <button
    @click="scrollToTop"
    class="position-fixed z-10 rounded-circle bg-white scroll-button border-0"
  >
    <img src="/webicon.svg" alt="scrollToTop" />
  </button>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref, watchEffect } from 'vue'
import IconLogo from './icons/IconLogo.vue'
import IconFB from './icons/IconFB.vue'
import IconIG from './icons/IconIG.vue'
import IconYT from './icons/IconYT.vue'
import IconLine from './icons/IconLine.vue'
import { scrollToTop } from '../composables/scrollToTop'

const menuIsShow = ref(false)
function menuToggle() {
  menuIsShow.value = !menuIsShow.value
}
watchEffect(() => {
  menuIsShow.value
    ? (document.body.style.overflow = 'hidden')
    : (document.body.style.overflow = 'auto')
})
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables';
@import '~bootstrap/scss/mixins';

.mt-100px {
  margin-top: 100px;
}
.menu {
  height: calc(100dvh - 66px);
  overflow: auto;
  top: 66px;
  width: 100dvw;
  transition: height 0.5s linear;
  position: absolute;
}
.h-0 {
  height: 0px;
}
.scroll-button {
  top: 55vh;
  right: 5%;
  transform: rotate(90deg);
  width: clamp(60px, 4vw, 134px);
  height: clamp(60px, 4vw, 134px);
  padding: 12px 8px 16px;
  filter: drop-shadow(10px 14px 14px rgba(0, 0, 0, 0.1));
}
.icon-logo {
  top: 50px;
  max-width: 85px;
  height: auto;
  left: 50%;
}
@include media-breakpoint-up(xxl) {
  .icon-logo {
    top: -24px;
    max-width: 158px;
    max-height: 158px;
  }
}

.header {
  max-height: 127px;
  overflow: visible;
}
</style>
