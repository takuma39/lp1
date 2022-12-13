<script setup lang="ts">
import { ref, reactive, computed } from "vue";
import SectionReverse from "@/components/layouts/section/SectionReverseLayout.vue";
import Person from "./PersonComponent.vue";
import PersonJson from "@/assets/json/person.json";
import FadeUp from "@/components/parts/animationFade/FadeComponent.vue";

//変数
let tab = ref<String>("trainer");
//クローン
const copyPerson = reactive(JSON.parse(JSON.stringify(PersonJson)));

//関数
const changeTab = (type: string) => {
  tab.value = type;
};
</script>

<template>
  <SectionReverse>
    <template v-slot:title-en>Our Trainer</template>
    <template v-slot:title-ja>トレーナー</template>
    <template v-slot:body>
      <div class="tab">
        <div class="tab__area">
          <div
            class="tab__btn"
            :class="{ 'tab--active': tab === 'trainer' }"
            @:click="changeTab('trainer')"
          >
            トレーナー
          </div>
          <div
            class="tab__btn"
            :class="{ 'tab--active': tab === 'staff' }"
            @:click="changeTab('staff')"
          >
            スタッフ
          </div>
        </div>
        <div class="tab__contents">
          <template v-for="person in copyPerson" :key="person.id">
            <FadeUp v-show="tab === person.type">
              <Person
                :image="`./static/images/person/${person.img}`"
                :alt="person.alt"
                :text="person.text"
              />
            </FadeUp>
          </template>
        </div>
      </div>
    </template>
  </SectionReverse>
</template>
<style scoped lang="scss">
@import "@/assets/sass/app2.scss";
.tab__area {
  display: grid;
  margin-bottom: 20px;
  grid-template-columns: repeat(2, 1fr);
}

.tab__btn {
  cursor: pointer;
  @include font-size(16);
  color: #fff;
  text-align: center;
  padding: 5px 0 10px 0;
}
.tab--active {
  position: relative;
  font-weight: bold;
  color: #fff;
}

.tab--active::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  border-radius: 3px;
  background-color: #fff;
}

.tab__contents {
  display: grid;
  row-gap: 15px;

  // $break3: 600;
  @include mq(o-br3) {
    display: grid;
    column-gap: 15px;
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
