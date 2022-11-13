<script setup lang="ts">
import { computed } from "vue";
import { RouterLink } from "vue-router";
import Heading from "@/components/parts/heading/HeadingPrimaryComponent.vue";

const props = defineProps({
  count: {
    type: Number,
    required: false,
  },
});
</script>
<template>

</template>

<style scoped lang="scss">
@import "@/assets/sass/app2.scss";

</style>
