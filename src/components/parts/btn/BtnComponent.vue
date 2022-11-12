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
  padding-right: 18px + 18px;
  transition: 0.3s;
  text-align: center;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #fff;
  border-radius: 50px;
  background-image: $color-btn;
  background-size: 200% auto;

  &::after {
    position: absolute;
    top: 50%;
    right: 1.5em;
    font-family: "Font Awesome 5 Free";
    font-weight: 900;
    content: "\f0da";
    transition: 0.3s;
    -webkit-transform: translateY(-50%);
    transform: translateY(-50%);

    @include font-size(14);
  }

  &:hover {
    text-decoration: none;
    background-position: right center;
    &::after {
      right: 1.2em;

      // $break4: 768;
      @include mq(u-br4) {
        right: 1.5em;
      }
    }
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
