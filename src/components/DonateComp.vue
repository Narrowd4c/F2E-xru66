<template>
  <div class="pb-20 pb-xl-0">
    <div class="container mx-auto">
      <SectionTitle
        class="mb-7 text-xl-center mx-xl-auto"
        sub-title="Donate"
        title="捐款方案"
      ></SectionTitle>
      <div class="mb-12 w-fit hstack mx-auto">
        <span>累計</span>
        <span class="ms-2 text-primary font-jost display-4">100,000,000</span>
      </div>
    </div>
    <swiper-container ref="swiperDonate" init="false">
      <template v-for="{ image, title, price, people } in donateList" :key="title">
        <swiper-slide class="swiper-donate-slide">
          <img :src="image" :alt="title" class="w-100" />
          <div class="position-absolute inset-0 p-0 container">
            <div
              class="donate-position mx-auto mx-xl-0 position-absolute mb-xl-10 py-4 px-8 pt-md-8 pb-md-12 px-md-12 bg-white bg-opacity-xl-75 rounded-3 w-fit ms-xl-auto shadow"
            >
              <h3 class="donate-card-title display-3 mb-2">{{ title }}</h3>
              <div class="mb-1 hstack">
                <p>捐款新台幣</p>
                <span class="donate-card-price ms-4 font-jost text-primary fw-bold"
                  >NT$ {{ price }}</span
                >
              </div>
              <p class="donate-card-people text-gray mb-9">
                已有<span class="px-1">{{ people }}</span> 人贊助
              </p>
              <button
                @click="showDonate(title)"
                class="border-0 donate-card-btn rounded-3 d-block text-center bg-primary text-white py-4"
              >
                前往捐款
              </button>
              <Teleport to="#app">
                <div
                  v-if="showDonateDialog && current === title"
                  @click.self="showDonateDialog = false"
                  class="w-100 h-100 z-3 inset-0 bg-black bg-opacity-50 position-fixed d-flex align-items-center justify-content-center"
                >
                  <div class="container text-center text-xl-start overflow-auto h-75 mh-100">
                    <div class="row bg-white position-relative rounded-2">
                      <img :src="image" :alt="title" class="col-xl-7 px-0" />
                      <div class="col-xl-5 px-10 py-10 py-xxl-30">
                        <div class="d-xl-flex mb-9 gap-4">
                          <h3 class="display-6">喵星人之友</h3>
                          <p class="text-gray mt-auto pb-2">
                            已有<span class="px-1">{{ people }}</span> 人贊助
                          </p>
                        </div>
                        <p class="mb-6 mb-xxl-20 text-start">
                          眾所皆知貓是外星人派來統治地球的。但牠們發現，只要一直喵喵叫，就能吃到很多好吃的，所以牠們決定要收人類為僕。除了飲食外，玩樂也是相當重要，要時刻注意主子的運動量，才能活得長長久久喔。
                        </p>
                        <p class="mb-2 mb-xxl-4">捐款新台幣</p>
                        <div class="row justify-content-center gap-4 font-jost mb-10">
                          <button
                            class="col-md-2 col-xl-3 order-1 order-xl-0 bg-white border-1 rounded-3 py-2 px-4 py-xxl-4 fs-5"
                          >
                            - $100
                          </button>
                          <p
                            class="col-12 col-xl order-0 donate-card-price mx-4 text-primary fw-bold"
                          >
                            NT ${{ price }}
                          </p>
                          <button
                            class="col-md-2 col-xl-3 order-1 order-xl-0 bg-white border-1 rounded-3 py-2 px-4 py-xxl-4 fs-5"
                          >
                            + $100
                          </button>
                        </div>
                        <button
                          class="mb-4 border-0 donate-card-btn rounded-3 w-100 d-block text-center bg-primary text-white py-4"
                        >
                          捐款
                        </button>
                        <form>
                          <input
                            class="me-2"
                            v-model="isAgree"
                            type="checkbox"
                            name="agree"
                            id="agree"
                          />
                          <label for="agree"
                            >勾選已同意<a href="#" class="text-decoration-underline text-primary"
                              >捐款聲明</a
                            ></label
                          >
                        </form>
                        <button
                          @click="showDonateDialog = false"
                          class="position-absolute top-0 end-0 bg-white bg-opacity-0 border-0 p-2 p-xl-8"
                        >
                          <span class="material-symbols-outlined"> close </span>
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </Teleport>
            </div>
          </div>
        </swiper-slide>
      </template>
    </swiper-container>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import SectionTitle from './SectionTitle.vue'
import donate1 from '@/assets/images/donate1.png'
import donate2 from '@/assets/images/donate2.png'
import donate3 from '@/assets/images/donate3.png'

const donateList = ref([
  { image: donate1, title: '喵星人之友', price: '600', people: '9,957' },
  { image: donate2, title: '喵星大使', price: '6,000', people: '2,000' },
  { image: donate3, title: '喵星傳奇', price: '600', people: '999' }
])
const isAgree = ref(false)

const swiperDonate = ref()
const swiperParams = {
  loop: true,
  slidesPerView: 1,
  speed: 1000
}
onMounted(() => {
  Object.assign(swiperDonate.value, swiperParams)
  swiperDonate.value?.initialize()
})

const showDonateDialog = ref(false)
const current = ref('')
function showDonate(val: string) {
  showDonateDialog.value = true
  current.value = val
}
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables';
@import '~bootstrap/scss/mixins';

swiper-container::part(container) {
  overflow-y: visible;
  overflow-x: clip;
}
.donate-position {
  bottom: 0%;
  right: 0%;
  left: 0%;
  transform: translate(0%, 80%);
}
@include media-breakpoint-up(sm) {
  .donate-position {
    transform: translate(0%, 50%);
  }
}
@include media-breakpoint-up(xl) {
  .donate-position {
    transform: translate(0%, 0%);
  }
}

.donate-card {
  &-title {
    font-weight: 800;
    line-height: 1.2;
    letter-spacing: 13px;
  }
  &-price {
    font-size: 30px;
    line-height: 166.667%;
    letter-spacing: 1.8px;
  }
  &-btn {
    width: 352px;
  }
}

.dialog {
  &-title {
    font-size: 30px;
    font-weight: 700;
    line-height: 50px;
    letter-spacing: 7.2px;
  }
}

</style>
