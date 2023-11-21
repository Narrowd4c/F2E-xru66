<script setup lang="ts">
import { RouterView } from 'vue-router'
import Footer from './components/FooterComp.vue'
import Header from './components/HeaderComp.vue'
import { useHead, useSeoMeta } from '@unhead/vue'
import ogImage from '@/assets/images/OIG_2.png'

const ogImg = new URL(ogImage, window.location.origin).href;

useHead({
  title: '2024 喵立漢立委競選網站',
  link: [
    {
      rel: 'icon',
      href: './webicon.svg'
    }
  ],
})

useSeoMeta({
  ogTitle: "2024 喵立漢立委競選網站",
  description: "2024 喵立漢立委的政績政策介紹與小額贊助",
  ogDescription: "2024 喵立漢立委的政績政策介紹與小額贊助",
  ogImage: window.location.origin + ogImage,
  ogUrl: window.location.origin + import.meta.env.BASE_URL,
  ogImageWidth: 800,
  ogImageHeight: 450,
  ogType: "website",
})

</script>

<template>
  <Header></Header>
  <RouterView />
  <Footer></Footer>
</template>

<style lang="scss"></style>
