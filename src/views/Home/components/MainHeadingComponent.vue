<script setup lang="ts">
import BgText from "@/components/parts/animationText/BgTextComponent.vue";
import Btn from "@/components/parts/btn/BtnComponent.vue";
</script>

<template>
  <div class="mv">
    <div class="mv__titleArea">
      <h2 class="mv__title">
        <BgText>
          <span class="mv__textBg">Body Make</span>
        </BgText>
        <br />
        <BgText>
          <span class="mv__textBg">
            <span class="mv__colorText">&</span>English
          </span>
        </BgText>
      </h2>
      <p class="mv__subTitle">
        <span class="mv__textBg">英会話＆パーソナルトレーニングジム</span>
      </p>
      <div class="mv__btn">
        <Btn link="/">無料カウンセリングを受ける</Btn>
      </div>
    </div>
    <div class="mv__img"></div>
  </div>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";

.mv {
  position: relative;
  height: 410px;
  padding-top: 150px;
  padding-left: 20px;

  // $break3: 600;
  @include mq(o-br3) {
    height: 500px;
    padding-left: 5%;
  }

  // $break6: 1140;
  @include mq(o-br6) {
    max-width: 1800px;
    height: 680px;
    padding-top: 220px;
    padding-left: 12%;
  }
}

.mv__title {
  font-size: min(11vw, 90px);
  font-style: italic;
  font-weight: inherit;
  line-height: 1.01;
  margin-bottom: 10px;

  // $break6: 1140;
  @include mq(o-br6) {
    margin-bottom: 20px;
  }
}

.mv__subTitle {
  font-size: min(3.5vw, 28px);
  font-weight: bold;
  line-height: 1;
  margin-bottom: 15px;

  // $break6: 1140;
  @include mq(o-br6) {
    margin-bottom: 30px;
  }
}

.mv__textBg {
  background-color: #fff;
}

.mv__colorText {
  font-size: min(9vw, 85px);
  color: $color-primary;
}

.mv__img {
  position: absolute;
  top: 0;
  right: 0;
  z-index: -1;
  opacity: 0;
  width: 70%;
  height: 410px;
  border-radius: 0 0 0 50px;
  background-image: url(/static/images/hero/bg_mv.jpg);
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  animation: 1s fadeInMvImg 0.2s forwards;

  // $break3: 600;
  @include mq(o-br3) {
    height: 500px;
  }
  // $break6: 1140;
  @include mq(o-br6) {
    height: 680px;
    border-radius: 0 0 0 90px;
  }
}

@keyframes fadeInMvImg {
  100% {
    opacity: 1;
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
