<template>
  <div class="w-fit mx-auto mx-xl-0 text-center text-xl-start">
    <h3 class="fs-2 text-primary mb-2 ps-2">{{ subTitle }}</h3>
    <h2 class="fs-xxl-80px display-3 text-secondary title-max-width">{{ title }}</h2>
  </div>
</template>

<script setup lang="ts">
defineProps({
  subTitle: {
    type: String,
    required: true,
    default: 'subTitle'
  },
  title: {
    type: String,
    required: true,
    default: 'title'
  },
  width: {
    type: String,
    default: 'fit-content'
  }
})
</script>

<style lang="scss">
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables.scss';
@import '~bootstrap/scss/mixins';

@include media-breakpoint-up(xxl){
  .fs-xxl-80px{
    font-size:80px !important;
  }
}
.title-max-width {
  white-space: pre-wrap;
  max-width: v-bind(width);
}
</style>
