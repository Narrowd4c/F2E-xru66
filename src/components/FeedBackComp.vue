<template>
  <div class="container">
    <div class="row align-items-center">
      <div class="col-6">
        <SectionTitle class="mb-15" sub-title="FeedBack" title="民眾服務信箱"></SectionTitle>
        <h3 class="mb-18px">您的聲音，我們的行動！</h3>
        <p class="me-10 w-75">
          親愛的鄉親，每一位市民的意見都是我們社區前進的原動力。無論大小事，我都誠摯希望聽到您的建議。分享您的想法，一同為我們的未來打造更美好！
        </p>
      </div>
      <div class="bg h-100 py-20 px-15 col-6 text-gray shadow">
        <div class="mb-6">
          <label for="name" class="mb-2">姓名</label>
          <input class="border-0 w-100 px-4 py-2" type="text" id="name" placeholder="請輸入姓名" />
        </div>
        <div class="mb-6">
          <label for="email" class="mb-2">Email</label>
          <input
            class="border-0 w-100 px-4 py-2"
            type="email"
            id="email"
            placeholder="請輸入電子郵件"
          />
        </div>
        <div class="mb-6">
          <label for="phone" class="mb-2">手機</label>
          <input
            class="border-0 w-100 px-4 py-2"
            type="number"
            id="phone"
            placeholder="請輸入手機"
          />
        </div>
        <div class="mb-6">
          <label for="comment" class="mb-10">建言</label>
          <textarea
            class="border-0 h-214 w-100 px-4 py-2"
            type="text"
            id="comment"
            placeholder="請輸入"
          ></textarea>
        </div>
        <button class="border-0 rounded-3 w-100 py-4 bg-primary text-white">送出</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import SectionTitle from '@/components/SectionTitle.vue'
</script>

<style scoped>
.bg {
  background: rgba(234, 127, 27, 0.1);
}
.h-214 {
  height: 214px;
}
.me-130 {
  margin-right: 130px;
}
</style>
