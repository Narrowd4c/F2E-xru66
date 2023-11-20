<template>
  <header class="border-bottom border-2 border-primary">
    <div class="header overflow-visible container py-5 py-lg-13 d-lg-flex fw-bold">
      <ul
        class="d-none justify-content-between flex-grow-1 me-12 me-xl-23 d-lg-flex font-jost fs-5 nav-font"
      >
        <li><a href="#about">About Me</a></li>
        <li>
          <a href="#last-activity">Last Activity</a>
        </li>
        <li><a href="#policy">Policy</a></li>
        <li><IconLogo class="position-relative icon-logo z-1"></IconLogo></li>
        <li><a href="#donate">Donate</a></li>
        <li><a href="#feedback">Feedback</a></li>
      </ul>
      <SocialMedia class="d-none d-lg-flex gap-6 ms-auto" :is-rounded="false"></SocialMedia>
      <div class="d-lg-none text-primary lh-1">
        <span @click="menuToggle" v-show="!menuIsShow" class="material-symbols-outlined">
          menu
        </span>
        <span @click="menuToggle" v-show="menuIsShow" class="material-symbols-outlined">
          close
        </span>
        <IconLogo class="position-absolute start-50 translate-middle z-3 icon-logo"></IconLogo>
      </div>
    </div>
    <div :class="{ 'h-0': !menuIsShow }" class="px-8 bg-white z-2 menu">
      <ul class="font-jost md:fs-5 mt-100px text-center fw-bold">
        <li v-for="{ sectionName, link } in navbar" :key="sectionName" class="mb-13">
          <a @click="menuToggle" :href="link">{{ sectionName }}</a>
        </li>
      </ul>
      <SocialMedia
        class="pt-13 pb-30 border-top gap-4 d-flex justify-content-center"
        :is-rounded="true"
      ></SocialMedia>
    </div>
  </header>
  <ScrollTop></ScrollTop>
    
</template>

<script setup lang="ts">
import { ref, watchEffect } from 'vue'
import IconLogo from './icons/IconLogo.vue'
import SocialMedia from './SocialMedia.vue'
import ScrollTop from './ScrollTop.vue'

const navbar = ref([
  { sectionName: 'About', link: '#about' },
  { sectionName: 'Last Activity', link: '#last-activity' },
  { sectionName: 'Policy', link: '#policy' },
  { sectionName: 'Donate', link: '#donate' },
  { sectionName: 'Feedback', link: '#feedback' }
])

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

.nav-font {
  line-height: 166.667%;
  letter-spacing: 1.08px;
}
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

.icon-logo {
  top: 50px;
  max-width: 85px;
  height: auto;
}
@include media-breakpoint-up(lg) {
  .icon-logo {
    top: -8px;
    max-width: 108px;
    max-height: 108px;
  }
}
@include media-breakpoint-up(xl) {
  .icon-logo {
    top: -24px;
    max-width: 158px;
    max-height: 158px;
  }
}

.header {
  max-height: 127px;
}
</style>
