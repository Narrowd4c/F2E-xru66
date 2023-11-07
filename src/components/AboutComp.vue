<script setup lang="ts">
import IrregularSvg from '@/components/IrregularSvg.vue'
</script>
<template>
  <div class="container mt-490 d-flex">
    <div class="w-50 mt-42">
      <h3 class="fs-2 text-primary mb-2">About Me</h3>
      <h2 class="display-1 text-secondary mb-20">立法委員<br />候選人主張</h2>
      <p class="about-article">
        我堅信，藉由推動更完善的貓咪福利和相關政策，更是間接地投資於台灣的未來。畢竟，民眾的身心健康與工作熱情是推動經濟的核心動力。透過完善的貓咪福利政策，為台灣的
        GDP 經濟帶來巨大效益。
        因此，我期望能在立法院內推進這些政策，確保每一隻貓咪都能得到他們應有的照顧，同時也為台灣的經濟發展助一臂之力。讓我們一同護航台灣的幸福經濟，從照顧每一隻貓咪開始。
      </p>
    </div>
    <div class="ms-auto ms-fix position-relative">
      <img src="@/assets/images/about-cat.png" alt="avatar" class="avatar" />
      <IrregularSvg class="irregular-svg position-absolute -z-10"></IrregularSvg>
      <div class="name-wrap position-absolute">
        <h1 class="name">喵立翰</h1>
        <h2 class="name-en font-jost">Miao Li-Han</h2>
        <div class="fish position-absolute">
          <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon" />
          <img src="@/assets/images/fishicon.svg" alt="" class="fish-icon-sm" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.mt-490 {
  margin-top: 490px;
}
.mt-42 {
  margin-top: 42px;
}

.about-article {
  line-height: 30px;
  letter-spacing: 3.84px;
}
.avatar {
  width: clamp(0px, 100%, 600px);
  height: clamp(0px, 100%, 600px);
  border-radius: 50%;
}
.irregular-svg {
  width: clamp(0px, 100%, 600px);
  height: clamp(0px, 100%, 532px);
  top: 30%;
  right: -15%;
}

.name-wrap {
  bottom: 7%;
  right: 0px;
}

.name {
  font-size: 80px;
  font-weight: 800;
  line-height: 1.25; /* 125% */
  letter-spacing: 22.4px;
  margin-right: -22.4px;
}
.name-en {
  font-size: 50px;
  font-weight: 500;
  letter-spacing: 4px;
}
.fish-icon {
  width: 148px;
  height: 71px;
  transform: translateX(-50%);
}

.fish {
  transform: translate(40%, 50%);
}
.fish-icon-sm {
  width: 98px;
  height: 47px;
  transform: translate(-70%, 100%);
}
@media screen and (min-width: 1500px) and (max-width: 1600px) {
  .ms-fix {
    margin-left: 1.5rem !important;
  }
}
</style>
