<script setup lang="ts">
import { ref } from "vue";
import { RouterLink } from "vue-router";
import Btn from "@/components/parts/btn/BtnComponent.vue";

//ページ内スクロール
let isActive = ref<boolean>(false);
window.addEventListener("scroll", () => {
  let position: number = document.documentElement.scrollTop;

  if (position > 200) {
    isActive.value = true;
  } else {
    isActive.value = false;
  }
});
</script>

<template>
  <header class="header" :class="{ 'is-active': isActive }">
    <h1 class="logo">
      <router-link to="/">
        <img alt="logo" src="@/assets/images/logo/logo.svg" />
      </router-link>
    </h1>
    <div class="header__btn" :class="{ 'is-active': isActive }">
      <Btn link="/">無料カウンセリングを受ける</Btn>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "@/assets/sass/app2.scss";
.header {
  display: flex;
  position: fixed;
  z-index: 100;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 60px;
  padding: 0 20px;
  transition: 0.3s;

  // $break6: 1140;
  @include mq(o-br6) {
    height: 80px;
  }

  .logo {
    width: 50px;
  }

  &.is-active {
    background-color: #fff;
    box-shadow: 0 3px 6px rgb(0 0 0 / 5%);
  }

  &__btn {
    transition: 0.3s;
    pointer-events: none;
    opacity: 0;
    &.is-active {
      pointer-events: auto;
      opacity: 1;
    }
  }
}

::v-deep(.btn) {
  @include font-size(12);
  padding: 12px 18px;

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(15);
  }
}
</style>
