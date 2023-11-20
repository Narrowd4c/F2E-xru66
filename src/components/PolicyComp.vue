<template>
  <div class="container">
    <SectionTitle class="mb-15" sub-title="Policy" title="政策議題"></SectionTitle>
    <div class="policy bg-primary bg-opacity-10 position-relative">
      <swiper-container
        ref="swiperPolicy"
        init="false"
        class="pb-15 pb-xl-0 swiper-policy-container"
      >
        <swiper-slide
          class="h-auto d-flex align-items-center"
          v-for="{ title, image, contents } in policyList"
          :key="title"
        >
          <div class="row policy-card px-8 py-xl-20 justify-content-center align-items-xl-start">
            <img class="col-lg-8 col-xl-7 p-0 pe-xl-6 policy-card-img" :src="image" :alt="title" />
            <div class="col-lg-8 col-xl-5 p-0 ps-xl-6 align-self-start">
              <h3 class="policy-card-title fw-bold">{{ title }}</h3>
              <ol class="policy-card-content">
                <li v-for="content in contents" :key="content.slice(0, 10)">
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
      <img class="position-absolute policy-fish-1" src="@/assets/images/fishicon.svg" alt="fish-icon" aria-hidden="true"/>
      <img class="position-absolute policy-fish-2" src="@/assets/images/fishicon.svg" alt="fish-icon" aria-hidden="true" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import SectionTitle from './SectionTitle.vue'
import PolicyImg1 from '@/assets/images/policy1.png'
import PolicyImg2 from '@/assets/images/policy2.png'
const policyList = ref([
  {
    image: PolicyImg1,
    title: '為毛孩子謀福利！推動寵物醫療保障方案',
    contents: [
      '街上氣氛真設立寵物醫療基金：每年撥款新台幣 10 億元，專款專用於支援家庭寵物的醫療費用',
      '提供醫療補助：每隻寵物每年可獲得高達新台幣 20,000 元的醫療補助，減輕飼主的經濟壓力',
      '合作動物醫院：目前已有和超過 200 家動物醫院進行初步的合作討論的很棒，從小孩到大人，甚至有些狗狗朋友都帶著貓耳來找我握手，真的太可愛了！這次的活動不僅讓我看到大家的熱情，更加堅定了我推進「貓咪友善環境」政策的決心。'
    ]
  },
  {
    image: PolicyImg2,
    title: '為毛孩子謀福利！推動寵物醫療保障方案',
    contents: [
      '街上氣氛真設立寵物醫療基金：每年撥款新台幣 10 億元，專款專用於支援家庭寵物的醫療費用',
      '提供醫療補助：每隻寵物每年可獲得高達新台幣 20,000 元的醫療補助，減輕飼主的經濟壓力',
      '合作動物醫院：目前已有和超過 200 家動物醫院進行初步的合作討論的很棒，從小孩到大人，甚至有些狗狗朋友都帶著貓耳來找我握手，真的太可愛了！這次的活動不僅讓我看到大家的熱情，更加堅定了我推進「貓咪友善環境」政策的決心。'
    ]
  }
])

const swiperPolicy = ref()

const swiperParams = {
  direction: 'horizontal',
  scrollbar: {
    el: '.swiper-policy-scrollbar',
    draggable: true,
    dragClass: 'swiper-policy-scrollbar-drag'
  },
  autoHeight: true,
  slidesPerView: 1,
  breakpoints: {
    1200: {
      direction: 'vertical'
    }
  }
}
onMounted(() => {
  Object.assign(swiperPolicy.value, swiperParams)
  swiperPolicy?.value.initialize()
})
</script>

<style lang="scss">
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables.scss';
@import '~bootstrap/scss/mixins';

.policy {
  margin-top: 20%;
  border-radius: 8px;
}
@include media-breakpoint-up(xl) {
  .policy {
    margin-left: 10%;
    margin-top: 0px;
  }
}
.swiper-policy-container::part(container) {
  overflow-y: visible;
  overflow-x: clip;
}

@include media-breakpoint-up(xl) {
  .swiper-policy-container::part(container) {
    margin-left: -10%;
    overflow: hidden;
  }
}
.swiper-policy-scrollbar {
  width: 25%;
  height: 3px;
  background: gray;
  position: absolute;
  right: 40%;
  top: 180px;
}
@include media-breakpoint-up(sm) {
  .swiper-policy-scrollbar {
    top: 200px;
  }
}
@include media-breakpoint-up(md) {
  .swiper-policy-scrollbar {
    top: 300px;
  }
}
@include media-breakpoint-up(lg) {
  .swiper-policy-scrollbar {
    top: 200px;
  }
}

.swiper-policy-scrollbar-drag {
  height: 2px;
  background: $primary !important;
}
@include media-breakpoint-up(xl) {
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
}
.policy-card {
  &-img {
    max-height: 458px;
    margin-top: -20%;
    margin-bottom: 60px;
  }
  @include media-breakpoint-up(xl) {
    &-img {
      margin-top: 0px;
    }
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
    right: -6%;
    bottom: -78px;
    max-width: 246px;
  }
}
</style>
