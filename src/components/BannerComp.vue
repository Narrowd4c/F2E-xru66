<script setup lang="ts">
import BannerBackground from '@/components/BannerBackground.vue'
import BannerBackgroundMd from '@/components/BannerBackgroundMd.vue'
</script>

<template>
  <div class="position-relative">
    <BannerBackgroundMd class="d-md-none -z-10 w-100"></BannerBackgroundMd>
    <BannerBackground class="d-none d-md-block -z-10 w-100" />
    <div class="container">
      <div class="position-absolute top-0">
        <h2 class="mx-auto banner-text text-secondary text-center text-md-start">
          台灣的明天，<br />喵先鋪路
        </h2>
        <div class="fish">
          <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon" />
          <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon-sm" />
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables';
@import '~bootstrap/scss/mixins';

.fish {
  margin-top: calc(120vw + 10px);
}
@include media-breakpoint-up(md) {
  .fish {
    margin-top: calc(8vw);
  }
}
.fish-icon {
  max-width: 88px;
  transform: translateX(-50%);
}
.fish-icon-sm {
  max-width: 58px;
  transform: translate(-60%, 100%);
}
@include media-breakpoint-up(xl) {
  .fish {
    margin-top: calc(6vw);
  }
  .fish-icon {
    max-width: 148px;
    max-height: 71px;
  }

  .fish-icon-sm {
    max-width: 98px;
    max-height: 47px;
  }
}
</style>
