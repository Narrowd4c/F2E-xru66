<template>
  <div class="position-relative">
    <BannerBackgroundMd class="d-md-none z-n1 w-100"></BannerBackgroundMd>
    <BannerBackground class="d-none d-md-block z-n1 w-100" />
    <div class="container">
      <div class="position-absolute top-0">
        <h2 class="mx-auto banner-text text-secondary text-center text-md-start">
          台灣的明天，<br />喵先鋪路
        </h2>
        <div class="fish">
          <img src="@/assets/images/fishicon.svg" aria-hidden="true" alt="fish-icon" class="fish-icon" />
          <img src="@/assets/images/fishicon.svg" aria-hidden="true"  alt="fish-icon" class="fish-icon-sm" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import BannerBackground from '@/components/BannerBackground.vue'
import BannerBackgroundMd from '@/components/BannerBackgroundMd.vue'
</script>


<style lang="scss" scoped>
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables';
@import '~bootstrap/scss/mixins';
.banner-text{
  font-weight: 800;
  font-size: 40px;
  letter-spacing: 12px;
  padding-top: 52px;
}
@include media-breakpoint-up(xl) {
  .banner-text{
  font-size: clamp(10px, calc(40px + 2dvw), 100px);
  letter-spacing: calc(30px - 1dvw);
  padding-top: calc(60px + 2dvw);
}
}

@include media-breakpoint-up(xxl) {
  .banner-text {
    font-size: clamp(10px, calc(40px + 3dvw), 100px);
    letter-spacing: 30px;
    padding-top: 139px;
  }
}
.fish {
  margin-top: calc(120vw);
}

.fish-icon {
  max-width: 88px;
  transform: translateX(0%);
}
.fish-icon-sm {
  max-width: 58px;
  transform: translate(0%, 100%);
}
@include media-breakpoint-up(sm) {
  .fish {
    margin-top: calc(120vw);
  }
}
@include media-breakpoint-up(md) {
  .fish {
    margin-top: calc(8vw);
  }
}

@include media-breakpoint-up(xxl) {
  .fish {
    margin-top: calc(6vw);
  }
  .fish-icon {
    max-width: 148px;
    max-height: 71px;
    transform: translateX(-50%);
  }
  .fish-icon-sm {
    max-width: 98px;
    max-height: 47px;
    transform: translate(-60%, 100%);
  }
}
</style>
