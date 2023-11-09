<script setup lang="ts">
import { ref, onMounted } from 'vue'
import SectionTitle from './SectionTitle.vue'
import PolicyImg1 from '@/assets/images/policy1.png'
import PolicyImg2 from '@/assets/images/policy2.png'
const policyList = ref([{
  image: PolicyImg1,
  title: '為毛孩子謀福利！推動寵物醫療保障方案',
  contents: [
    '街上氣氛真設立寵物醫療基金：每年撥款新台幣 10 億元，專款專用於支援家庭寵物的醫療費用',
    '提供醫療補助：每隻寵物每年可獲得高達新台幣 20,000 元的醫療補助，減輕飼主的經濟壓力',
    '合作動物醫院：目前已有和超過 200 家動物醫院進行初步的合作討論的很棒，從小孩到大人，甚至有些狗狗朋友都帶著貓耳來找我握手，真的太可愛了！這次的活動不僅讓我看到大家的熱情，更加堅定了我推進「貓咪友善環境」政策的決心。'
  ],
},
{
  image: PolicyImg2,
  title: '為毛孩子謀福利！推動寵物醫療保障方案',
  contents: [
    '街上氣氛真設立寵物醫療基金：每年撥款新台幣 10 億元，專款專用於支援家庭寵物的醫療費用',
    '提供醫療補助：每隻寵物每年可獲得高達新台幣 20,000 元的醫療補助，減輕飼主的經濟壓力',
    '合作動物醫院：目前已有和超過 200 家動物醫院進行初步的合作討論的很棒，從小孩到大人，甚至有些狗狗朋友都帶著貓耳來找我握手，真的太可愛了！這次的活動不僅讓我看到大家的熱情，更加堅定了我推進「貓咪友善環境」政策的決心。'
  ],
}])

const swiperPolicy = ref()

const swiperParams = {
  direction: 'vertical',
  scrollbar: {
    el: '.swiper-policy-scrollbar',
    draggable: true,
    dragClass: 'swiper-policy-scrollbar-drag'
  },
  autoHeight: true,
  slidesPerView: 1,
  loop: true
}
onMounted(() => {
  Object.assign(swiperPolicy.value, swiperParams)
  swiperPolicy?.value.initialize()
})
</script>

<template>
  <div class="container">
    <SectionTitle class="mb-15" sub-title="Policy" title="政策議題"></SectionTitle>
    <div class="policy position-relative">
      <swiper-container ref="swiperPolicy" init="false">
        <swiper-slide class="h-auto d-flex align-items-center" v-for="{title, image, contents} in policyList" :key="title">
          <div class="row policy-card py-20">
            <img class="col-7 p-0 pe-6 policy-card-img" :src="image" :alt="title" />
            <div class="col-5 p-0 ps-6 align-self-start">
              <h3 class="policy-card-title fw-bold">{{ title }}</h3>
              <ol class="policy-card-content" v-for="content in contents" :key="content.slice(0,10)">
                <li>
                  <p>
                    {{ content }}
                  </p>
                </li>
              </ol>
            </div>
          </div>
        </swiper-slide>
      </swiper-container>
      <div class="swiper-policy-scrollbar"></div>
      <img class="position-absolute policy-fish-1" src="@/assets/images/fishicon.svg" alt="" />
      <img class="position-absolute policy-fish-2" src="@/assets/images/fishicon.svg" alt="" />
    </div>
  </div>
</template>
<style lang="scss">
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables.scss';
.policy {
  margin-left: 10%;
  background: rgba(234, 127, 27, 0.1);
  border-radius: 8px;
  swiper-container::part(container) {
    margin-left: -10%;
    position: relative;
  }
}
.swiper-policy-scrollbar {
  width: 1px;
  height: 150px;
  background: gray;
  position: absolute;
  right: 5%;
  top: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  justify-content: center;
}
.swiper-policy-scrollbar-drag {
  flex: 0 0 3px;
  background: $primary !important;
}

.policy-card {
  &-img {
    max-height: 458px;
  }
  &-title {
    font-size: 30px;
    line-height: 166.667%;
    letter-spacing: 7.2px;
    margin-bottom: 1.125rem;
  }
  &-content {
    line-height: 187.5%;
    letter-spacing: 3.84px;
  }
}
.policy-fish {
  &-1 {
    max-width: 158px;
    right: 10%;
    bottom: -30px;
  }
  &-2 {
    right: -3%;
    bottom: -50px;
    max-width: 246px;
  }
}
</style>
