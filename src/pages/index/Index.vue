<script setup lang="ts">
import {useI18n} from "vue-i18n";

import GradeList from "../../components/index/GradeList.vue";
import SillageTitle from "../../components/common/SillageTitle.vue";
import LanguageSwitch from "../../components/index/LanguageSwitch.vue";
import FunctionEntrance from "../../components/index/FunctionEntrance.vue";
import BookmarkArea from "../../components/index/UserBookmarkArea.vue";
import {useStore} from "../../store/store";

const {t} = useI18n();
const store = useStore();
</script>

<template>
  <div class="index-body">
    <div class="title-area">
      <sillage-title size="150px"></sillage-title>
      <language-switch></language-switch>
    </div>

    <grade-list/>
    <function-entrance/>
    <bookmark-area v-show="store.bookmarks.length>0"/>
  </div>
</template>

<style scoped>
.index-body {
  min-height: 100vh;
  background-image: linear-gradient(rgba(100, 200, 250, 30%) 10%, rgba(100, 200, 250, 10%), rgba(100, 200, 250, 30%));
}

.title-area {
  padding-top: 50px;
}
</style>
