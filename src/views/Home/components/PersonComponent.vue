<script setup lang="ts">
const props = defineProps({
  image: {
    type: String,
    required: false,
    default: "",
  },
  alt: {
    type: String,
    required: false,
    default: "",
  },
  text: {
    type: String,
    required: false,
    default: "",
  },
});
</script>

<template>
  <div class="person fadeUpEffect">
    <figure class="person__img">
      <img :src="props.image" :alt="props.alt" />
    </figure>
    <div class="person__body">
      <div class="person__text">
        <p v-html="props.text"></p>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.person {
  overflow: hidden;
  border-radius: 10px;
  background-color: #fff;
  height: 100%;
}

.person__body {
  padding: 20px;
}

.person__text {
  @include font-size(14);
  line-height: 1.6;

  // $break6: 1140;
  @include mq(o-br6) {
    @include font-size(15);
    line-height: 1.7;
  }
}
</style>
