<script setup lang="ts">
import SectionNormal from "@/components/layouts/section/SectionNormal.vue";
import Swiper from "@/components/parts/swiper/SwiperComponent.vue";
</script>
<template>
  <SectionNormal>
    <template v-slot:title-en>Studio</template>
    <template v-slot:title-ja>スタジオ</template>
    <template v-slot:body>
      <Swiper :count="3">
        <template v-slot:1>
          <img src="@/assets/images/studio/studio01.jpg" alt="" />
        </template>
        <template v-slot:2>
          <img src="@/assets/images/studio/studio02.jpg" alt="" />
        </template>
        <template v-slot:3>
          <img src="@/assets/images/studio/studio03.jpg" alt="" />
        </template>
      </Swiper>
    </template>
  </SectionNormal>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";

</style>
