<script setup lang="ts">
import SectionNormal from "@/components/layouts/section/SectionNormal.vue";
import Accordinon from "@/components/parts/accordion/AccordionComponent.vue";
import FaqJson from "@/assets/json/faq.json";
</script>

<template>
  <SectionNormal>
    <template v-slot:title-en>FAQ</template>
    <template v-slot:title-ja>よくあるご質問</template>
    <template v-slot:body>
      <div class="faq">
        <Accordinon v-for="n in FaqJson" :key="n.id">
          <template v-slot:btn>{{ n.question }}</template>
          <template v-slot:content>{{ n.answer }}</template>
        </Accordinon>
      </div>
    </template>
  </SectionNormal>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.faq {
  margin-top: -20px;
}
</style>
