<script setup lang="ts">
import Section from "@/components/layouts/section/SectionLayout.vue";
import Fade from "@/components/parts/animationFade/FadeComponent.vue";
</script>

<template>
  <Section class="about">
    <div class="about__body">
      <ul class="about__list">
        <li class="about__box">
          <figure class="about__imgWrapper">
            <img
              class="about__img"
              src="@/assets/images/about/about-training.jpg"
              alt="英語でトレーニングの様子"
            />
          </figure>
          <Fade class="about__desc">
            <div class="about__subtitle">Training</div>
            <h2 class="about__title">
              セッションはすべて英語。<br />LAさながらの環境
            </h2>
            <div class="about__text">
              <p>
                ネイティブスピーカーによる50分のパーソナルトレーニングはすべて英語です！アップテンポの洋楽が流れる空間でテンション高めのトレーナーが英語であなたのトレーニングを盛り上げてくれます。ダイエットでよく使う英語をまとめたオリジナルテキストもあるのでスピーキング学習もバッチリです！<br />英語に苦手意識がある方は日本人トレーナーも選べますのでご安心してください。
              </p>
            </div>
          </Fade>
        </li>
        <li class="about__box" data-type="reverse">
          <figure class="about__imgWrapper">
            <img
              class="about__img"
              src="@/assets/images/about/about-food.jpg"
              alt="低糖質の食事メニュー"
            />
          </figure>
          <Fade class="about__desc">
            <div class="about__subtitle about__subtitle--food">
              Food
            </div>
            <h2 class="about__title">
              低糖質レストランを完備！<br />美味しく食べてダイエット
            </h2>
            <div class="about__text">
              <p>
                食事制限って大変ですよね......。でも大丈夫！ENGBODY館内には低糖質レストラン『LCR』を完備しています。Low
                carb（低糖質）なのにとっても美味しい味に驚くはずです！メニューも豊富で飽きさせません。美味しく食べてしっかり痩せる！しかも英語力もアップ！それがENGBODYなのです。
              </p>
            </div>
          </Fade>
        </li>
      </ul>
    </div>
  </Section>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";

.about {
  // $break6: 1140;
  @include mq(o-br6) {
    max-width: 1300px;
    margin: 0 auto;
  }
}
.about__list {
  display: grid;
  row-gap: 40px;

  // $break6: 1140;
  @include mq(o-br6) {
    row-gap: 100px;
  }
}

.about__box {
  // $break6: 1140;
  @include mq(o-br6) {
    position: relative;
  }
}

.about__box[data-type="reverse"] {
  // $break6: 1140;
  @include mq(o-br6) {
    display: flex;
    justify-content: right;
  }
}

.about__imgWrapper {
  width: 100%;

  // $break6: 1140;
  @include mq(o-br6) {
    width: 70%;
  }
}

.about__desc {
  position: relative;
  margin: -10px 20px;
  padding: 40px 30px 30px 30px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);

  // $break6: 1140;
  @include mq(o-br6) {
    position: absolute;
    right: 20px;
    bottom: -20px;
    width: 555px;
    margin: 0;
    padding: 60px;
  }
}

.about__box[data-type="reverse"] .about__desc {
  // $break6: 1140;
  @include mq(o-br6) {
    left: 20px;
  }
}

.about__subtitle {
  font-size: 18px;
  color: var(--main-color);
  margin-bottom: 20px;

  // $break6: 1140;
  @include mq(o-br6) {
    font-size: 24px;
  }
}

.about__subtitle--food {
  color: #00b21b;
}

.about__title {
  font-size: 22px;
  font-weight: bold;
  line-height: 1.5;
  margin-bottom: 15px;

  // $break6: 1140;
  @include mq(o-br6) {
    font-size: 32px;
  }
}

.about__text {
  font-size: 14px;
  line-height: 1.7;

  // $break6: 1140;
  @include mq(o-br6) {
    font-size: 15px;
    line-height: 1.8;
  }
}

.about__btn {
  margin-top: 40px;
  padding: 0 20px;

  // $break6: 1140;
  @include mq(o-br6) {
    margin-top: 70px;
  }
}
</style>
