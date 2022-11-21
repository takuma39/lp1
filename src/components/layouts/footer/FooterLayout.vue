<script setup lang="ts">
import { RouterLink } from "vue-router";
</script>

<template>
  <footer class="footer">
    <h2 class="heading">ENGBODY</h2>
    <div class="copyright">
      <a href="." class="copyright__link">&copy;portfolio</a>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@import "@/assets/sass/app2.scss";
.footer {
  padding: 60px 30px;
  background-color: $color-secondary;
}

.heading {
  text-align: center;
  @include font-size(20);
  color: #fff;
}

.copyright {
  margin-top: 30px;
  text-align: center;

  @include font-size(10);
  &__link {
    text-decoration: none;
    color: #fff;
    &:hover {
      text-decoration: none;
      opacity: 0.8;
    }
  }
}
</style>
