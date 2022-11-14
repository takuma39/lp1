<script setup lang="ts">
import Heading from "@/components/parts/heading/HeadingPrimaryComponent.vue";
</script>

<template>
  <section class="trainer section section--color-reverse">
    <svg
      class="section-border-top"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 375 25"
    >
      <path
        d="M375,240.667l-20.833,1.38c-20.833,1.484-62.5,4.089-104.167,1.406-41.667-2.786-83.333-11.12-125-15.286S41.667,224,20.833,224H0v25H375Z"
        transform="translate(0 -224)"
        fill="#eb51c2"
      />
    </svg>
    <div class="section__inner">
      <div class="section__container">
        <div class="section__heading">
          <Heading type="reverse">
            <template v-slot:en><slot name="title-en"></slot></template>
            <template v-slot:ja><slot name="title-ja"></slot></template>
          </Heading>
        </div>
        <div class="section__Body">
          <slot name="body"></slot>
        </div>
      </div>
    </div>
    <svg
      class="section-border-bottom"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 375 25"
    >
      <path
        d="M375,240.667l-20.833,1.38c-20.833,1.484-62.5,4.089-104.167,1.406-41.667-2.786-83.333-11.12-125-15.286S41.667,224,20.833,224H0v25H375Z"
        transform="translate(375 249) rotate(180)"
        fill="#eb51c2"
      />
    </svg>
  </section>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
@include sectionFrame(true);
</style>
