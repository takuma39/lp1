<script setup lang="ts">
import { RouterLink } from "vue-router";
const props = defineProps({
  type: {
    type: String,
    required: false,
    default: "A",
  },
  link: {
    type: String,
    required: false,
    default: "",
  },
});
</script>

<template>
  <router-link :to="props.link" class="btn" :data-type="props.type">
    <slot></slot>
  </router-link>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.btn {
  @include font-size(14);
  position: relative;
  font-weight: bold;
  display: inline-block;
  padding: 18px;
  transition: 0.3s;
  text-align: center;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  border-radius: 50px;

  &:hover {
    text-decoration: none;
  }
}

.btn[data-type="A"] {
  color: #fff;
  background-image: $color-btn;
  background-size: 200% auto;

  &:hover {
    background-position: right center;
  }
}

.btn[data-type="B"] {
  background-image: none;
  background-color: #fff;
  color: $color-primary;
  transition: all 0.3s;

  &:hover {
    opacity: 0.8;
  }
}
</style>
