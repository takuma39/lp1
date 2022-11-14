<script setup lang="ts">
import { computed } from "vue";
const props = defineProps({
  type: {
    type: String,
    required: false,
    default: "",
  },
});
</script>
<template>
  <h2 class="heading-primary" :data-type="props.type">
    <slot name="en" />
    <span class="heading-primary__subtitle">
      <slot name="ja" />
    </span>
  </h2>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.heading-primary {
  font-size: 40px;
  line-height: 1;
  color: #333;

  // $break6: 1140;
  @include mq(o-br6) {
    font-size: 64px;
  }
}

.heading-primary__subtitle {
  display: block;
  font-size: 14px;
  font-weight: bold;
  color: var(--main-color);
  margin-top: 10px;

  // $break6: 1140;
  @include mq(o-br6) {
    font-size: 20px;
    margin-top: 10px;
  }
}

.heading-primary[data-type="reverse"],
.heading-primary[data-type="reverse"] .heading-primary__subtitle {
  color: #fff;
}
</style>
