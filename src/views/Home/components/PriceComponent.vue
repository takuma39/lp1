<script setup lang="ts">
import SectionReverse from "@/components/layouts/section/SectionReverseLayout.vue";
import PriceCard from "./PriceCardComponent.vue";
import PriceJson from "@/assets/json/price.json";
import { ref, onMounted } from "vue";

//テス数
const target = ref<any>();

//変数
let fade = ref<boolean>(true);

//onMounted
onMounted(() => {
  target.value.addEventListener("scroll", () => {
    if (target.value.scrollLeft > 20) {
      fade.value = false;
    } else {
      fade.value = true;
    }
  });
});
</script>
<template>
  <SectionReverse>
    <template v-slot:title-en>Price</template>
    <template v-slot:title-ja>料金</template>
    <template v-slot:body>
      <div class="price" ref="target">
        <PriceCard
          v-for="n in PriceJson"
          :key="n.id"
          :label="n.label"
          :plan="n.plan"
          :price="n.price"
          :admissionFee="n.admissionFee"
          :rental="n.rental"
          :restaurant="n.restaurant"
          :guidance="n.guidance"
        />
        <transition name="fade">
          <div class="price__scroll" v-show="fade">
            <span class="price__scroll-icon material-icons-round">east</span
            >スクロール
          </div>
        </transition>
      </div>
    </template>
  </SectionReverse>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.price {
  margin: 0 -30px;
  position: relative;
  white-space: nowrap;
  margin-top: -25px;
  padding-top: 25px;
  padding-right: 20px;
  overflow-x: auto;
}

.price__scroll {
  position: absolute;
  top: 50%;
  right: 5%;
  @include font-size(12);
  color: #fff;
  padding: 10px;
  transform: translateY(-50%);
  border-radius: 4px;
  background-color: rgba(0, 0, 0, 0.6);
}

.price__scroll-icon {
  display: block;
  @include font-size(40);
  text-align: center;
}

// $break6: 1140;
@include mq(o-br6) {
  .price__body {
    margin: 0;
  }

  .price {
    margin: 0;
    display: grid;
    padding-right: 0;
    column-gap: 15px;
    grid-template-columns: repeat(3, 1fr);
  }

  .price__scroll {
    display: none;
  }
}

.fade {
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
