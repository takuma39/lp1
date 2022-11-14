<script setup lang="ts">
import Sns from "@/components/parts/sns/SnsComponent.vue";

import MV from "./components/MVComponent.vue";
import Intro from "./components/IntroComponent.vue";
import About from "./components/AboutComponent.vue";
import SectionReverse from "@/components/layouts/section/SectionReverseLayout.vue";
import SectionNormal from "@/components/layouts/section/SectionNormal.vue";
</script>

<template>
  <main>
    <MV />
    <Intro />
    <About />
    <SectionReverse>
      <template v-slot:title-en>aaaa</template>
      <template v-slot:title-ja>あああ</template>
    </SectionReverse>

    <SectionNormal>
      <template v-slot:title-en>aaaa</template>
      <template v-slot:title-ja>あああ</template>
    </SectionNormal>
    <Sns url="/" title="test" description="test" />
  </main>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";

// ブレイクポイント見本
.test {
  // over
  // $break1: 340;
  @include mq(o-br1) {
  }
  // $break2: 480;
  @include mq(o-br2) {
  }
  // $break3: 600;
  @include mq(o-br3) {
  }
  // $break4: 768;
  @include mq(o-br4) {
  }
  // $break5: 960;
  @include mq(o-br5) {
  }
  // $break6: 1140;
  @include mq(o-br6) {
  }
  // under
  // $break6: 1140;
  @include mq(u-br6) {
  }
  // $break5: 960;
  @include mq(u-br5) {
  }
  // $break4: 768;
  @include mq(u-br4) {
  }
  // $break3: 600;
  @include mq(u-br3) {
  }
  // $break2: 480;
  @include mq(u-br2) {
  }
  // $break1: 380;
  @include mq(u-br1) {
  }
  // $break1: 330;
  @include mq(u-br0) {
  }
}
</style>
