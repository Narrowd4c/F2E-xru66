<script setup lang="ts">
import IconFB from './icons/IconFB.vue'
import IconIG from './icons/IconIG.vue'
import IconYT from './icons/IconYT.vue'
import IconLine from './icons/IconLine.vue'
</script>

<template>
    <footer class="border">
    <div class="container pt-75 pb-110 mx-auto row">
      <div class="col">
        <h5 class="mb-10 font-jost">Information</h5>
        <ul>
          <li class="mb-8">
            <img class="me-18px" src="/address.png" alt="address">
            <a href="#">喵星區，毛茸茸大道88號，喵喵大樓3樓</a></li>
          <li class="mb-8">
            <img class="me-18px" src="/phone.png" alt="phone">
            <a href="tel:+02-888-5678">(02) 888-5678</a></li>
          <li>
            <img class="me-18px" src="/email.svg" alt="email"><a href="mailto:@meowoffice@linmeow.tw">meowoffice@linmeow.tw</a>
          </li>
        </ul>
      </div>
      <div class="col font-jost">
        <h5 class="mb-10">Links</h5>
        <ul class="row gap-y-14">
          <li class="col-5"><a class="text-primary" href="#">About me</a></li>
          <li class="col-5"><a href="#" class="font-jost text-primary">Feedback</a></li>
          <li><a href="#" class="text-primary">Last activity</a></li>
          <li><a href="#" class="text-primary">Policy</a></li>
          <li><a href="#" class="text-primary">Donate</a></li>
        </ul>
      </div>
      <div class="d-flex flex-column col">
        <h5 class="mb-10 font-jost">Follow us</h5>
        <ul class="row mb-15">
          <li class="col">
            <a href="#" class="rounded-circle p-5 border"><IconFB /></a>
          </li>
          <li class="col">
            <a href="#" class="rounded-circle p-5 border"><IconIG /></a>
          </li>
          <li class="col">
            <a href="#" class="rounded-circle p-5 border"><IconYT /></a>
          </li>
          <li class="col">
            <a href="#" class="rounded-circle p-5 border"><IconLine /></a>
          </li>
        </ul>
        <p class="mt-auto">版權聲明：© 2023喵立翰 版權所有</p>
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