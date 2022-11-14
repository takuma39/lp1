<script setup lang="ts">
import Heading from "@/components/parts/heading/HeadingPrimaryComponent.vue";
</script>

<template>
  <section class="section">
    <div class="section__container">
      <div class="section__heading">
        <slot name="title"></slot>
        <Heading>
          <template v-slot:en><slot name="title-en"></slot></template>
          <template v-slot:ja><slot name="title-ja"></slot></template>
        </Heading>
      </div>
      <div class="studio__body section__body">
        <slot name="body"></slot>
      </div>
    </div>
  </section>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
@include sectionFrame();
</style>
