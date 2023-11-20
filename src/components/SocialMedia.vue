<template>
  <ul>
    <li v-for="{name, img} in images" :key="name">
      <a href="#" :class="{'rounded-circle p-5 border':isRounded}"><component :is="img"></component></a>
    </li>
  </ul>
</template>

<script setup lang="ts">
import { shallowRef } from 'vue'
import IconFB from './icons/IconFB.vue'
import IconIG from './icons/IconIG.vue'
import IconYT from './icons/IconYT.vue'
import IconLine from './icons/IconLine.vue'
const props = defineProps({
    isRounded: {
        type: Boolean,
        default: false,
    }
})

const images = shallowRef([
    { name:'FaceBook', img: IconFB }, { name:'Instagram', img: IconIG }, { name:'Youtube' ,img: IconYT }, { name:'Line' ,img: IconLine }])
</script>

<style lang="scss" scoped></style>
