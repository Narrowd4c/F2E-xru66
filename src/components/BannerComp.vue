<script setup lang="ts">
import BannerBackground from '@/components/BannerBackground.vue'
</script>

<template>
  <div>
    <BannerBackground class="position-absolute -z-10 w-100" />
    <div class="container">
      <h2 class="banner-text">台灣的明天,<br />喵先鋪路</h2>
      <div class="fish position-absolute">
        <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon" />
        <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon-sm" />
      </div>
    </div>
  </div>
</template>
<style scoped>
.fish-icon {
  width: 148px;
  height: 71px;
  transform: translateX(-50%);
}

.fish {
  margin-top: 107px;
}
.fish-icon-sm {
  width: 98px;
  height: 47px;
  transform: translate(-60%, 100%);
}
</style>
