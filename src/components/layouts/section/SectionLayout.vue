<script setup lang="ts"></script>

<template>
  <section class="section">
    <slot></slot>
  </section>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.section {
  padding: 20px 0;

  // $break6: 1140;
  @include mq(o-br6) {
    padding: 30px 0;
  }
}
</style>
