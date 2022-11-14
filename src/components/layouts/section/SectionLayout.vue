<script setup lang="ts"></script>

<template>
  <section class="section">
    <slot></slot>
  </section>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.section {
  @include section();
}
</style>
