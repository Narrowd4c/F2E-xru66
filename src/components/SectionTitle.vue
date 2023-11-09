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
  }
})
</script>

<style lang="scss">
.title-max-width {
  white-space: pre-wrap;
  max-width: 9ch;
}

</style>

<template>
  <div class="width-fit">
    <h3 class="fs-2 text-primary mb-2">{{ subTitle }}</h3>
    <h2 class="display-1 text-secondary title-max-width">{{ title }}</h2>
  </div>
</template>
