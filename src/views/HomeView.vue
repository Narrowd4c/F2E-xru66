<script setup lang="ts">
import BannerComp from '@/components/BannerComp.vue'
import AboutComp from '@/components/AboutComp.vue'
import LastActivity from '@/components/LastActivity.vue'
import PolicyComp from '@/components/PolicyComp.vue';
import DonateComp from '@/components/DonateComp.vue';
</script>

<template>
  <main>
    <BannerComp />
    <AboutComp class="mb-257"></AboutComp>
    <LastActivity></LastActivity>
    <PolicyComp></PolicyComp>
    <DonateComp></DonateComp>
  </main>
  
</template>
<style lang="scss" scoped>
.mb-257{
  margin-bottom: 257px;
}
</style>