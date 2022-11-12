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
  color: #fff;
  border-radius: 50px;
  background-image: $color-btn;
  background-size: 200% auto;

  &:hover {
    text-decoration: none;
    background-position: right center;
  }
}

.btn[data-type="block"] {
  display: block;
  max-width: 300px;
  margin: 0 auto;
}

.btn[data-type="center"] {
  display: block;
  margin-right: auto;
  margin-left: auto;
}

.btn[data-type="transparent"] {
  border: 1px solid #fff;
  background: none;
  &:hover {
    opacity: 0.8;
  }
}
</style>
