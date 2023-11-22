<template>
  <button
    @click="scrollToTop"
    class="position-fixed z-3 rounded-circle bg-white scroll-button border-0"
  >
    <img src="/webicon.svg" alt="scrollToTop" />
  </button>
</template>

<script setup lang="ts">
import { scrollToTop } from "../composables/scrollToTop"
</script>

<style lang="scss" scoped>
.scroll-button {
  top: 55vh;
  right: 5%;
  transform: rotate(90deg);
  width: clamp(60px, 4vw, 134px);
  height: clamp(60px, 4vw, 134px);
  padding: 12px 8px 16px;
  filter: drop-shadow(10px 14px 14px rgba(0, 0, 0, 0.1));
}
</style>
