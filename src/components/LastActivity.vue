<script setup lang="ts">
import bg from '@/assets/images/last-active.svg'
import IrregularSvg from './IrregularSvg.vue'
</script>

<template>
  <div class="bg position-relative overflow-hidden">
    <!-- <img :src="bg"/> -->
    <IrregularSvg
      fill="rgb(255, 255, 255)"
      opacity="1"
      class="irregular position-absolute"
    />
    <div class="container">
      <h3 class="fs-2 text-primary mb-2">About Me</h3>
      <h2 class="display-1 text-secondary mb-20">立法委員<br />候選人主張</h2>
    </div>
  </div>
</template>

<style scoped>

.bg{
  background: url(../assets/images/last-active.svg) ;
  background-size: cover;
  width: 100%;
  height: 100%;
  padding-top: 150px;
  padding-bottom: 195px;
}
.irregular {
  width: 33%;
  height: 32.5%;
  transform: rotate(166.897deg);
  top: -15%;
  left: -5%;
}
</style>
