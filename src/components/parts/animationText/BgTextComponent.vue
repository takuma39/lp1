<script setup lang="ts">
import { ref, onMounted } from "vue";
const target = ref<any>();

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      const firstEntry = entries[0];
      if (firstEntry.isIntersecting) {
        firstEntry.target.classList.add("bgextend");
      } else {
        firstEntry.target.classList.remove("bgextend");
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
  <span class="bgLRextendTrigger bgLRextend" ref="target">
    <span class="bgappearTrigger bgappear">
      <span class="mv__text-bg-color">
        <slot></slot>
      </span>
    </span>
  </span>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
/*全共通*/
.bgextend {
  position: relative;
  opacity: 0;
  overflow: hidden; /*はみ出た色要素を隠す*/
  animation-name: bgextendAnimeBase;
  animation-duration: 1s;
  animation-fill-mode: forwards;
}

@keyframes bgextendAnimeBase {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

/*中の要素*/
.bgextend .bgappear {
  opacity: 0;
  animation-name: bgextendAnimeSecond;
  animation-duration: 1s;
  animation-delay: 0.6s;
  animation-fill-mode: forwards;
}

@keyframes bgextendAnimeSecond {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

/*左から右*/
.bgextend.bgLRextend::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: $color-primary; /*伸びる背景色の設定*/
  animation-name: bgLRextendAnime;
  animation-duration: 1s;
  animation-fill-mode: forwards;
}
@keyframes bgLRextendAnime {
  0% {
    transform: scaleX(0);
    transform-origin: left;
  }
  50% {
    transform: scaleX(1);
    transform-origin: left;
  }
  50.001% {
    transform-origin: right;
  }
  100% {
    transform: scaleX(0);
    transform-origin: right;
  }
}

/*スクロールをしたら出現する要素にはじめに透過0を指定*/
.bgappearTrigger,
.bgLRextendTrigger {
  opacity: 0;
}
</style>
