<template>
  <div>
    <div class="container mx-auto">
      <SectionTitle
        class="mb-7 text-center mx-auto"
        sub-title="Donate"
        title="捐款方案"
      ></SectionTitle>
      <div class="mb-12 width-fit hstack mx-auto">
        <span>累計</span>
        <span class="ms-2 text-primary font-jost display-4">100,000,000</span>
      </div>
    </div>
    <swiper-container ref="swiperDonate" init="false">
      <template v-for="({ image, title, price, people }, i) in donateList" :key="i">
        <swiper-slide :style="{ '--bg': `url(${image})` }" class="position-relative">
          <img
            :src="image"
            :alt="title"
            class="position-absolute inset-0 h-100 object-top object-cover w-100 -z-10"
          />
          <div class="container">
            <div class="donate-card rounded-3 width-fit ms-auto">
              <h3 class="donate-card-title mb-2">{{ title }}</h3>
              <div class="mb-1 hstack">
                <p>捐款新台幣</p>
                <span class="donate-card-price ms-4 font-jost text-primary fw-bold"
                  >NT$ {{ price }}</span
                >
              </div>
              <p class="donate-card-people text-gray mb-9">
                已有<span class="px-1">{{ people }}</span> 人贊助
              </p>
              <RouterLink
                to="/"
                class="donate-card-link rounded-3 d-block text-center bg-primary text-white py-4"
                >前往捐款</RouterLink
              >
            </div>
          </div>
        </swiper-slide>
      </template>
    </swiper-container>
  </div>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref, onMounted } from 'vue'
import SectionTitle from './SectionTitle.vue'
import donate1 from '@/assets/images/donate1.jpeg'
import donate2 from '@/assets/images/donate2.png'
import donate3 from '@/assets/images/donate3.png'

const donateList = ref([
  { image: donate1, title: '喵星人之友', price: '600', people: '9,957' },
  { image: donate2, title: '喵星大使', price: '6,000', people: '2,000' },
  { image: donate3, title: '喵星傳奇', price: '600', people: '999' }
])

const swiperDonate = ref()
const swiperParams = {
  loop: true,
  slidesPerView: 1,
  autoplay: {
    delay: 2000
  },
  speed: 2000,
}
onMounted(() => {
  Object.assign(swiperDonate.value, swiperParams)
  swiperDonate.value?.initialize()
})
</script>

<style lang="scss" scoped>
.donate-card {
  margin-top: 367px;
  margin-bottom: 45px;
  padding: 30px 50px 50px;
  background: rgba(255, 255, 255, 0.7);
  &-title {
    font-size: 50px;
    font-weight: 800;
    line-height: 1.2;
    letter-spacing: 13px;
  }
  &-price {
    font-size: 30px;
    line-height: 166.667%;
    letter-spacing: 1.8px;
  }
  &-link {
    width: 352px;
  }
}

.inset-0 {
  inset: 0;
}
.object-cover {
  object-fit: cover;
}
.object-top {
  object-position: top;
}
</style>
