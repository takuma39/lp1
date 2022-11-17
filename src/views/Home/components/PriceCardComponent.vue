<script setup lang="ts">
const p_priceCard = defineProps({
  label: {
    type: String,
    required: false,
  },
  plan: {
    type: String,
    required: false,
  },
  price: {
    type: Number,
    required: false,
    default: 0,
  },
  admissionFee: {
    type: Number,
    required: false,
    default: 0,
  },
  rental: {
    type: String,
    required: false,
  },
  restaurant: {
    type: String,
    required: false,
  },
  guidance: {
    type: String,
    required: false,
  },
});

const formatPrice = p_priceCard.price.toLocaleString();
const formatAdmissionFee = p_priceCard.admissionFee.toLocaleString();
</script>

<template>
  <div class="priceCard">
    <div class="priceCard__label" v-if="p_priceCard.label">{{ p_priceCard.label }}</div>
    <h3 class="priceCard__plan">{{ p_priceCard.plan }}</h3>
    <div class="priceCard__priceList">
      <p class="priceCard__price"><span>¥</span>{{ formatPrice }}</p>
      <p class="priceCard__admissionFee">（入会金 ¥{{ formatAdmissionFee }}）</p>
    </div>
    <div class="priceCard__item">
      <h4 class="priceCard__itemTitle">レンタル</h4>
      <p class="priceCard__itemText">
        {{ p_priceCard.rental }}
      </p>
    </div>
    <div class="priceCard__item">
      <h4 class="priceCard__itemTitle">レストラン</h4>
      <p class="priceCard__itemText">{{ p_priceCard.restaurant }}</p>
    </div>
    <div class="priceCard__item">
      <h4 class="priceCard__itemTitle">食事指導</h4>
      <p class="priceCard__itemText">{{ p_priceCard.guidance }}</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.priceCard {
  display: inline-block;
  position: relative;
  width: 320px;
  text-align: center;
  margin-left: 20px;
  padding: 40px 20px 0;
  border-radius: 8px;
  background-color: #fff;
}

.priceCard__label {
  position: absolute;
  top: -24px;
  left: 50%;
  width: 80%;
  font-size: 20px;
  font-weight: bold;
  line-height: 1;
  color: $color-primary;
  padding: 10px;
  transform: translateX(-50%);
  border: 2px solid $color-primary;
  border-radius: 50px;
  background-color: #fff;
}

.priceCard__plan {
  @include font-size(26);
  font-weight: bold;
  color: $color-primary;
  margin-bottom: 10px;
}

.priceCard__priceList {
  padding-bottom: 20px;
}

.priceCard__price {
  @include font-size(48);
}

.priceCard__price span {
  @include font-size(40);
}

.priceCard__item {
  padding: 30px 0;
  border-top: 1px solid #ccc;
}

.priceCard__itemTitle {
  @include font-size(18);
  margin-bottom: 5px;
}

.priceCard__itemText {
  font-weight: bold;
}

// $break6: 1140;
@include mq(o-br6) {
  .priceCard {
    width: auto;
    margin: 0;
  }
}
</style>
