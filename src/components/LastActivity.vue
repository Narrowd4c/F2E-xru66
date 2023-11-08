<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { register } from 'swiper/element/bundle'
import IrregularSvg from './IrregularSvg.vue'
import OIG_1 from '@/assets/images/OIG_1.png'
import OIG_2 from '@/assets/images/OIG_2.png'
import OIG_3 from '@/assets/images/OIG_3.png'
// register Swiper custom elements
register()
const activies = ref([
  {
    date: '2023-12-26',
    title: '參與台北寵物論壇，爭取貓咪友善環境',
    content:
      '炎炎夏日的周六，我走進了台北寵物論壇，帶著一副貓耳髮箍，決定要全力宣傳「貓咪至上」的理念！我相信，我們的都市中，每一隻貓咪都應該有自己的 VIP 休憩空間。',
    image: OIG_1
  },
  {
    date: '2022-12-24',
    title: '掃街模式開啟！帶著你的貓耳，來和我一起走！',
    content:
      '街上氣氛真的很棒，從小孩到大人，甚至有些狗狗朋友都帶著貓耳來找我握手，真的太可愛了！這次的活動不僅讓我看到大家的熱情，更加堅定了我推進「貓咪友善環境」政策的決心。',
    image: OIG_2
  },
  {
    date: '2021-12-20',
    title: '收容所模特兒大比拼！',
    content:
      '今天的收容所不再是一片寂靜。為了讓更多人認識到這裡的毛孩子，我們舉辦了一場前所未有的「模特兒走秀」！',
    image: OIG_3
  },
  {
    date: '2023-12-26',
    title: '參與台北寵物論壇，爭取貓咪友善環境',
    content:
      '炎炎夏日的周六，我走進了台北寵物論壇，帶著一副貓耳髮箍，決定要全力宣傳「貓咪至上」的理念！我相信，我們的都市中，每一隻貓咪都應該有自己的 VIP 休憩空間。',
    image: OIG_1
  }
])
const swiperEl = ref({})
const swiperParams = {
  scrollbar: {
    el: '.swiper-scrollbar',
    draggable: true
  },
  spaceBetween: 32,
  slidesPerView: 3,
  breakpoints: {
    640: {
      slidesPerView: 2
    },
    1024: {
      slidesPerView: 3
    }
  }
}
function getYear(date: String) {
  return date.split('-')[0]
}
function getDate(date: String) {
  const formateDate = date.split('-').slice(1)
  return formateDate.join('/')
}
onMounted(() => {
  Object.assign(swiperEl.value, swiperParams)
  swiperEl.value.initialize()
})
</script>

<template>
  <div class="active-bg position-relative overflow-hidden">
    <IrregularSvg class="position-absolute irregular irregular-top"></IrregularSvg>
    <IrregularSvg class="position-absolute irregular irregular-bottom"></IrregularSvg>
    <div class="container">
      <h3 class="fs-2 text-primary mb-2">Last Activity</h3>
      <h2 class="display-1 text-secondary mb-20">最新活動</h2>
      <swiper-container ref="swiperEl" init="false" class="overflow-visible" slides-per-view="3">
        <swiper-slide v-for="{ image, title, content, date } in activies" :key="i">
          <div class="d-flex flex-column">
            <img :src="image" :alt="title" class="active-img" />
            <time class="active-date hstack gap-4 text-primary display-5"
              >{{ getYear(date) }}<span class="fs-2">{{ getDate(date) }}</span>
              <div class="border w-100"></div
            ></time>
            <h4 class="active-title mb-4 fw-bold">{{ title }}</h4>
            <p class="active-content">
              {{ content }}
            </p>
          </div>
        </swiper-slide>
      </swiper-container>
      <div class="mt-20">
        <div class="swiper-scrollbar mx-auto"></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables.scss';
@import '~bootstrap/scss/maps';
@import '~bootstrap/scss/mixins';
.active-bg {
  background: url(../assets/images/last-active.svg) center/cover no-repeat;
  padding-top: 150px;
  padding-bottom: 195px;
}
.irregular {
  width: 33%;
    height: 32.5%;
    transform: rotate(166.897deg);
  &-top {
    top: -15%;
    left: -5%;
  }
  &-bottom {
    top: 80%;
    right: -15%;
  }
}

swiper-container::part(container) {
  overflow: visible;
  position: static;
}

.swiper-scrollbar {
  width: 150px;
  margin-top: 20px;
  height: 3px;
  background: gray;
}
.swiper-scrollbar-drag {
  height: 3px !important;
  background: $primary !important;
  transform: translateY(-50%);
}
.active {
  &-img {
    object-fit: cover;
    object-position: center;
    max-height: 190px;
    @include media-breakpoint-up(xxl) {
      max-height: 253px;
    }
  }
  &-date {
    margin-top: 24px;
    margin-bottom: 46px;
  }
  &-title {
    line-height: 50px; /* 166.667% */
    letter-spacing: 7.2px;
    min-height: 100px;
  }
  &-content {
    line-height: 30px; /* 187.5% */
    letter-spacing: 3.84px;
  }
}
</style>
