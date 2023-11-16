<script setup lang="ts">
import SocialMedia from './SocialMedia.vue'
</script>

<template>
    <footer class="border">
    <div class="container pt-75 pb-110 mx-auto row flex-column flex-lg-row">
      <div class="col">
        <h5 class="mb-10 font-jost d-none d-lg-block">Information</h5>
        <ul class="text-center text-lg-start">
          <li class="mb-8 d-flex align-items-start justify-content-center justify-content-lg-start">
            <img class="pt-1 me-18px" src="/address.png" alt="address">
            <a href="#">喵星區，毛茸茸大道88號，喵喵大樓3樓</a></li>
          <li class="mb-8">
            <img class="me-18px" src="/phone.png" alt="phone">
            <a href="tel:+02-888-5678">(02) 888-5678</a></li>
          <li>
            <img class="me-18px" src="/email.svg" alt="email"><a href="mailto:@meowoffice@linmeow.tw">meowoffice@linmeow.tw</a>
          </li>
        </ul>
      </div>
      <div class="col font-jost d-none d-lg-block">
        <h5 class="mb-10">Links</h5>
        <ul class="row gap-y-14">
          <li class="col-5"><a class="text-primary" href="#about">About me</a></li>
          <li class="col-5"><a href="#feedback" class="font-jost text-primary">Feedback</a></li>
          <li><a href="#last-activity" class="text-primary">Last activity</a></li>
          <li><a href="#policy" class="text-primary">Policy</a></li>
          <li><a href="#donate" class="text-primary">Donate</a></li>
        </ul>
      </div>
      <div class="d-flex flex-column col mt-15 mt-lg-0">
        <h5 class="mb-10 font-jost d-none d-lg-block">Follow us</h5>
        <SocialMedia class="d-flex justify-content-center justify-content-lg-start gap-4 mb-15" :is-rounded="true"></SocialMedia>
        <p class="mt-auto text-center text-lg-start">版權聲明：© 2023喵立翰 版權所有</p>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.pt-75 {
  padding-top: 75px;
}
.pb-110 {
  padding-bottom: 110px;
}
.gap-y-14 {
  gap: 14px 0px;
}
</style>