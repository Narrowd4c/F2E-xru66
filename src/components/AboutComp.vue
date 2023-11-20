<script setup lang="ts">
import IrregularSvg from '@/components/IrregularSvg.vue'
import SectionTitle from '@/components/SectionTitle.vue'
</script>
<template>
  <div class="container d-grid grid-areas">
    <SectionTitle
      class="grid-title mb-6"
      sub-title="About Me"
      title="立法委員 候選人主張"
      width="9ch"
    ></SectionTitle>
    <p class="about-article grid-content me-xl-20 mt-20 mt-xl-0 mt-xl-20">
      我堅信，藉由推動更完善的貓咪福利和相關政策，更是間接地投資於台灣的未來。畢竟，民眾的身心健康與工作熱情是推動經濟的核心動力。透過完善的貓咪福利政策，為台灣的
      GDP 經濟帶來巨大效益。
      因此，我期望能在立法院內推進這些政策，確保每一隻貓咪都能得到他們應有的照顧，同時也為台灣的經濟發展助一臂之力。讓我們一同護航台灣的幸福經濟，從照顧每一隻貓咪開始。
    </p>
    <div class="grid-thumbnail mx-auto w-fit position-relative">
      <img src="@/assets/images/about-cat.png" alt="avatar" class="avatar" />
      <IrregularSvg class="irregular-svg position-absolute z-n1"></IrregularSvg>
      <div class="name-position position-absolute d-flex d-xl-block">
        <div class="order-2 position-relative bottom-50 start-sm-25 w-100 flex-grow-1">
          <h1 class="name">喵立翰</h1>
          <h2 class="name-en font-jost">Miao Li-Han</h2>
        </div>
        <div class="fish order-1 d-flex d-xl-block w-fit">
          <img src="@/assets/images/fishicon.svg" alt="icon" class="fish-icon" />
          <img src="@/assets/images/fishicon.svg" alt="small-icon" class="fish-icon-sm" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '~bootstrap/scss/functions';
@import '@/assets/scss/variables';
@import '~bootstrap/scss/mixins';
.d-grid {
  display: grid;
}

.grid-title {
  grid-area: title;
}
.grid-content {
  grid-area: content;
}
.grid-thumbnail {
  grid-area: thumbnail;
}
.grid-areas {
  grid-template-areas:
    'title'
    'thumbnail'
    'content';
}
@include media-breakpoint-up(xl) {
  .grid-areas {
    grid-template-areas:
      'title thumbnail thumbnail'
      'content thumbnail thumbnail'
      'content . . ';
  }
}
@include media-breakpoint-up(xl) {
  .grid-areas {
    grid-template-areas:
      'title title thumbnail thumbnail'
      'content content thumbnail thumbnail'
      'content content . .';
  }
}
.fish-icon {
  width: 100px;
  height: 100px;
}
.mt-42 {
  margin-top: 42px;
}

.about-article {
  line-height: 30px;
  letter-spacing: 3.84px;
}
.avatar {
  width: clamp(0px, 100%, 300px);
  height: clamp(0px, 100%, 300px);
  border-radius: 50%;
}
@include media-breakpoint-up(md) {
  .avatar {
    width: clamp(0px, 100%, 400px);
    height: clamp(0px, 100%, 400px);
  }
}
@include media-breakpoint-up(xl) {
  .avatar {
    width: clamp(0px, 100%, 600px);
    height: clamp(0px, 100%, 600px);
  }
}
.irregular-svg {
  width: clamp(0px, 100%, 600px);
  height: clamp(0px, 100%, 532px);
  top: 25%;
  right: -5%;
}
@include media-breakpoint-up(xl) {
  .irregular-svg {
    width: clamp(0px, 100%, 600px);
    height: clamp(0px, 100%, 532px);
    top: 30%;
    right: -15%;
  }
}

.name-position {
  bottom: 7px;
  right: 0px;
}
.name {
  font-size: 24px;
  font-weight: 800;
  line-height: 1.25;
  letter-spacing: 6.72px;
  padding-left: 6.72px;
}
@include media-breakpoint-up(xl) {
  .name {
    font-size: 80px;
    letter-spacing: 22.4px;
    padding-left: 22.4px;
  }
  .name-en {
    font-size: 50px;
    font-weight: 500;
    letter-spacing: 4px;
  }
}

.fish {
  transform: translate(40%, 50%);
}
.fish-icon {
  width: 148px;
  height: 71px;
  transform: translateX(-50%);
}
.fish-icon-sm {
  width: 98px;
  height: 47px;
  transform: translate(-70%, 100%);
}
</style>
