<script setup lang="ts">
import { RouterView } from 'vue-router'
import Footer from './components/FooterComp.vue'
import Header from './components/HeaderComp.vue'
import { useHead } from '@unhead/vue'
useHead({
  title: '2024 喵立漢立委競選網站',
  link: [
    {
      rel: 'icon',
      href: '/webicon.svg'
    }
  ],
  meta: [
    { property: 'og:image', content: '/og-img.png' },
    { property: 'og:image:width', content: 900 },
    { property: 'og:image:height', content: 450 },
    { property: 'og:title', content: '2024 喵立漢立委競選網站' },
    { property: 'og:description', content: '2024 喵立漢立委的政績政策介紹與小額贊助' },
    { name: 'description', content: '2024 喵立漢立委的政績政策介紹與小額贊助 ' },
    { property: 'og:type', content: 'website' }
  ]
})
</script>

<template>
  <Header></Header>
  <RouterView />
  <Footer></Footer>
</template>

<style lang="scss"></style>
