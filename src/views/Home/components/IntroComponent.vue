<script setup lang="ts"></script>

<template>
  <section class="intro">
    <h3 class="intro__title">
      YOU CAN <br class="intro__title-br" />
      DO IT!
    </h3>
    <h4 class="intro__subtitle">英語とトレーニングの<span>蜜月関係</span></h4>
    <div class="intro__text">
      Hey, guys! 英語を話している時ってなんだかテンションが上りませんか？<br />
      バイブス高めでトレーニングをすれば、あなたのベストなパフォーマンスが出せます！<br />
      英語と運動に自信がなくたってOK！<br />
      優しくて盛り上げな上手な外国人トレーナーがしっかりサポートします。<br />
      さぁ、ENGBODYで英語でパーソナルトレーニングを受けましょう。
    </div>
  </section>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.intro {
  margin-top: -20px;
  padding: 0 20px;
}

.intro__title {
  @include font-size(56);
  font-style: italic;
  font-weight: 700;
  line-height: 1;
  color: $color-primary;
  text-align: center;

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(108);
    margin-bottom: 10px;
  }
}

.intro__subtitle {
  @include font-size(16);
  font-weight: bold;
  letter-spacing: 0.1em;
  text-align: center;
  margin-bottom: 25px;

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(32);
    margin-bottom: 25px;
  }
}

.intro__subtitle span {
  color: $color-primary;
}

.intro__text {
  @include font-size(15);
  line-height: 1.8;

  // $break3: 600;
  @include mq(o-br3) {
    max-width: 720px;
    text-align: center;
    margin: 0 auto;
  }

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(16);
    line-height: 2;
  }
}

.intro__title-br {
  // $break3: 600;
  @include mq(o-br3) {
    display: none;
  }
}
</style>
