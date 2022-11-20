<script setup lang="ts">
import { ref } from "vue";

//変数
let open = ref<boolean>(false);

//関数
const toggle = () => {
  open.value = !open.value;
};
</script>

<template>
  <div class="accordion">
    <div class="accordion__btn" :class="{ 'is-active': open }" @click="toggle">
      <span class="accordion__label">Q</span>
      <p class="accordion__text">
        <slot name="btn"></slot>
      </p>
    </div>
    <div class="accordion__content" :class="{ 'is-active': open }">
      <span class="accordion__label">A</span>
      <p class="accordion__text">
        <slot name="content"></slot>
      </p>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.accordion {
  border-bottom: 1px solid #ccc;
}

.accordion__btn {
  display: flex;
  column-gap: 15px;
  position: relative;
  font-weight: normal;
  padding: 20px 30px 15px 0;
  cursor: pointer;

  &::after {
    display: block;
    content: "expand_more";
    position: absolute;
    top: 50%;
    right: 0;
    font-family: "Material Icons Round";
    font-size: 24px;
    color: $color-primary;
    transform: translateY(-50%);
  }

  &.is-active::after {
    content: "expand_less";
  }
}

.accordion__content {
  display: flex;
  column-gap: 15px;
  opacity: 0;
  visibility: hidden;
  padding-bottom: 0px;
  height: 0px;
  transition: opacity 0.2s, visibility 0.2s, padding-bottom 0.5s, height 0.5s;

  &.is-active {
    opacity: 1;
    visibility: visible;
    padding-bottom: 15px;
    height: 40px;
  }
}

.accordion__label {
  flex: 0 25px;
  font-size: 26px;
  font-weight: bold;
  color: $color-primary;
  text-align: center;
}

.accordion__text {
  @include font-size(15);
  line-height: 1.7;
}
</style>
