<script setup lang="ts">
import {zhCN, dateZhCN, enUS, dateEnUS, frFR, dateFrFR} from "naive-ui";
import {computed} from "vue";
import {useI18n} from "vue-i18n";

const {locale} = useI18n();

const naiveLocaleConfig = computed(() => {
  switch (locale.value) {
    case "en":
      return {locale: enUS, date: dateEnUS};
    case "fr":
      return {locale: frFR, date: dateFrFR};
    default:
      return {locale: zhCN, date: dateZhCN};
  }
});
</script>

<template>
  <div class="trilingual-naive-container">
    <n-config-provider :locale="naiveLocaleConfig.locale" :date-locale="naiveLocaleConfig.date">
      <slot></slot>
    </n-config-provider>
  </div>

</template>

<style scoped>
.trilingual-naive-container {
  width: 100%;
}
</style>