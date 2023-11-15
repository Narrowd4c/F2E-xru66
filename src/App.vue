<script setup lang="ts">
import { RouterView } from 'vue-router'
import Footer from './components/FooterComp.vue'
import Header from './components/HeaderComp.vue'
</script>

<template>
  <Header></Header>
  <RouterView />
  <Footer></Footer>
</template>

<style lang="scss">

</style>