<script setup lang="ts">
import Btn from "@/components/parts/btn/BtnComponent.vue";
</script>

<template>
  <div class="cta">
    <div class="cta__img">
      <picture>
        <source media="(max-width: 768px)" srcset="@/assets/images/cta/sp_cta.jpg" />
        <img src="@/assets/images/cta/pc_cta.jpg" alt="ジムのメンバーとトレーナー" />
      </picture>
    </div>
    <div class="cta__body">
      <div class="cta__title">Come join us!!</div>
      <div class="cta__btn">
        <Btn link="/" type="B">無料カウンセリングを受ける</Btn>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import "@/assets/sass/app2.scss";
.cta {
  padding-top: 30px;

  // $break6: 1140;
  @include mq(o-br6) {
    padding-top: 40px;
  }
}

.cta__body {
  text-align: center;
  padding: 30px 20px;
  background-color: $color-primary;

  // $break6: 1140;
  @include mq(o-br6) {
    padding: 50px 20px;
  }
}

.cta__title {
  @include font-size(26);
  color: #fff;
  margin-bottom: 10px;

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(64);
    margin-bottom: 15px;
  }
}

::v-deep(.btn) {
  @include font-size(13);
  padding: 20px;
  padding-right: 20px + 18px;

  // $break3: 600;
  @include mq(o-br3) {
  }

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(20);
    padding: 30px;
    padding-right: 30px + 18px;
  }
}
</style>
