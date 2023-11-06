<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import IconCommunity from './components/icons/IconCommunity.vue'
import IconFB from './components/icons/IconFB.vue'
import IconIG from './components/icons/IconIG.vue'
import IconYT from './components/icons/IconYT.vue'
import IconLine from './components/icons/IconLine.vue'
</script>

<template>
  <div class="border-bottom border-2 border-primary">
  <header class="container py-51 header d-flex fw-bold ">
    <ul class="d-flex font-jost fs-5 justify-content-between flex-grow-1 me-lg-5 nav">
      <li class="nav-link-spacing1"><RouterLink to="/" class="d-block">About Me</RouterLink></li>
      <li class="nav-link-spacing1"><RouterLink to="/" class="d-block">Last Activity</RouterLink></li>
      <li><RouterLink to="/" >Policy</RouterLink></li>
      <li class="nav-icon-spacing test"><IconCommunity ></IconCommunity></li>
      <li class="nav-link-spacing2"><RouterLink to="/" class="d-block">Donate</RouterLink></li>
      <li ><RouterLink to="/" class="d-block">Feedback</RouterLink></li>
    </ul>
    <ul class="row ms-auto">
      <li class="col"><RouterLink to="/"><IconFB /></RouterLink></li>
      <li class="col"><RouterLink to="/"><IconIG /></RouterLink></li>
      <li class="col"><RouterLink to="/"><IconYT /></RouterLink></li>
      <li class="col"><RouterLink to="/"><IconLine /></RouterLink></li>
    </ul>
  </header>
  </div>
  <RouterView />
</template>

<style lang="scss">
   @import "~bootstrap/scss/functions";
   @import "./assets/scss/variables";
   @import '~bootstrap/scss/mixins';
   @include media-breakpoint-up(xxl) {
    .nav-link-spacing1{
    margin-right: 126px;
  }
  .nav-link-spacing2{
    margin-right: 89px;
  }
  .nav-icon-spacing{
    margin: 0 119px;
  }
   }
   .header{
    overflow: visible;
    max-height: 127px;
  }
  .nav{
    line-height: 166.667%;
    letter-spacing: 1.08px;
  }
   .test{
     position: relative;
     top: -28px;
   }
  .icon{
    width: 58px;
    height: 58px;
  }
  
  .py-51{
    padding-top: 51px;
    padding-bottom: 51px;
  }
  
</style>
