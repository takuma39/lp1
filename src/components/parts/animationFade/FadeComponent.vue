<script setup lang="ts"></script>

<template>
  <div class="fadeUpEffect fadeUp">
    <slot></slot>
  </div>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.fadeUpEffect {
  opacity: 0;
}

.fadeUp {
  opacity: 0;
  animation-name: fadeUp;
  animation-duration: 0.8s;
  animation-fill-mode: forwards;
}
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
