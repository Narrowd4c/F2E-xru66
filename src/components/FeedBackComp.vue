<template>
  <div class="container">
    <div class="row align-items-center">
      <div class="col-xl-6 pe-xl-20">
        <SectionTitle
          class="mb-6 mb-xl-15"
          sub-title="FeedBack"
          title="民眾服務信箱"
        ></SectionTitle>
        <h3 class="mb-3 mb-xl-4 text-center text-xl-start">您的聲音，我們的行動！</h3>
        <p class="font-space text-gray mb-6">
          親愛的鄉親，每一位市民的意見都是我們社區前進的原動力。無論大小事，我都誠摯希望聽到您的建議。分享您的想法，一同為我們的未來打造更美好！
        </p>
      </div>
      <div class="ms-auto col-xl-6">
        <form class="bg-primary bg-opacity-10 pt-6 pb-13 px-5 py-xl-20 px-xl-15 text-gray shadow">
          <div class="mb-6" v-for="{id, placeholder, label, type} in inputList" :key="id">
            <label :for="id" class="mb-2 font-space text-gray">{{ label }}</label>
            <input
              class="border-0 w-100 px-4 py-2 font-space text-gray"
              :type="type"
              :id="id"
              :placeholder="placeholder"
            />
          </div>
          <div class="mb-6 ">
            <label for="comment" class="mb-2 font-space">建言</label>
            <textarea
              class="border-0 h-214 w-100 px-4 py-2 font-space"
              type="text"
              id="comment"
            ></textarea>
          </div>
          <button class="border-0 rounded-3 w-100 py-4 bg-primary text-white">送出</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import SectionTitle from '@/components/SectionTitle.vue'
import { shallowRef } from 'vue'
const inputList = shallowRef([
  { id: 'user-name', placeholder: '請輸入姓名', label: '姓名', type:'text' },
  { id: 'email', placeholder: '請輸入 Email', label: 'Email' ,type:'email'},
  { id: 'phone', placeholder: '請輸入手機號碼', label: '手機' ,type:'text'},
])
</script>

<style scoped lang="scss">
.h-214 {
  height: 214px;
}
.font-space {
  line-height: 30px;
  letter-spacing: 3.84px;
}
</style>
