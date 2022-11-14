<script setup lang="ts">
import { ref, onMounted } from "vue";
const target = ref<any>();

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      const firstEntry = entries[0];
      if (firstEntry.isIntersecting) {
        firstEntry.target.classList.add("fadeUp");
      } else {
        firstEntry.target.classList.remove("fadeUp");
      }
    },
    {
      root: document,
      threshold: 0,
      rootMargin: "0px",
    }
  );
  observer.observe(target.value);
});
</script>

<template>
  <div class="fadeUpEffect" ref="target">
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
