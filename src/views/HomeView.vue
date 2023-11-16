<script setup lang="ts">
import BannerComp from '@/components/BannerComp.vue'
import AboutComp from '@/components/AboutComp.vue'
import LastActivity from '@/components/LastActivity.vue'
import PolicyComp from '@/components/PolicyComp.vue'
import DonateComp from '@/components/DonateComp.vue'
import FeedBackComp from '@/components/FeedBackComp.vue'
import { register } from 'swiper/element/bundle'
// register Swiper custom elements
register()


</script>

<template>
  <div>
    <BannerComp />
    <AboutComp id="about" class="mb-257"></AboutComp>
    <LastActivity id="last-activity" class="mb-150"></LastActivity>
    <PolicyComp id="policy" class="mb-217"></PolicyComp>
    <DonateComp id="donate" class="mb-150"></DonateComp>
    <FeedBackComp id="feedback" class="mb-314"></FeedBackComp>
  </div>
</template>
<style lang="scss">

.mb-490 {
  margin-bottom: 490px;
}
.mb-257 {
  margin-bottom: 257px;
}
.mb-217 {
  margin-bottom: 217px;
}
.mb-150 {
  margin-bottom: 150px;
}
.mb-314 {
  margin-bottom: 314px;
}
</style>
