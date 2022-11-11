<script setup lang="ts">
import { ref } from "vue";
import { RouterLink } from "vue-router";
import SpMenu from "@/components/layouts/spMenu/SpMenuLayout.vue";

//ページ内スクロール
let isActive = ref<boolean>(false);
window.addEventListener("scroll", () => {
  let position: number = document.documentElement.scrollTop;

  if (position > 520) {
    isActive.value = true;
  } else {
    isActive.value = false;
  }
});
</script>

<template>
  <transition name="active">
    <header class="header" v-show="isActive">
      <h1 class="logo">
        <router-link to="/">
          <img alt="FA EXHIBITION" src="@/assets/images/logo/logo.svg" />
        </router-link>
      </h1>
      <SpMenu />
    </header>
  </transition>
</template>

<style lang="scss">
@import "@/assets/sass/app2.scss";
.header {
  display: flex;
  position: fixed;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 86px;
  padding: 0 30px;
  transition: all 0.3s;
  z-index: 10;

  // $break4: 768;
  @include mq(u-br4) {
    height: 64px;
    padding: 0 15px;
  }

  .logo {
    width: 50px;
  }
}

.active {
  &-enter {
    &-from {
      opacity: 0;
    }
    &-to {
      opacity: 1;
    }
    &-active {
      transition: opacity 0.3s;
    }
  }
  &-leave {
    &-from {
      opacity: 1;
    }
    &-to {
      opacity: 0;
    }
    &-active {
      transition: opacity 0.3s;
    }
  }
}
</style>
