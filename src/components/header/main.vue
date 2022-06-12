<template>
  <header class="header">
    <span class="header__logo">Sportsman</span>
    <span class="header__settings">Settings</span>
  </header>
  <Tabs :tabs="tabs" :current-tab="currentTab" @click="switchTabs" />
  <component :is="tabs[currentTab]"></component>
</template>
<script setup>
  import Tabs from '../tabs/tabs.vue';
  import { ref } from 'vue';

  import Strength from '../main-pages/strength.vue';
  import Circuit from '../main-pages/circuit.vue';
  import Statistics from '../main-pages/statistics.vue';

  const currentTab = ref('Strength');
  const tabs = {
    Strength,
    Circuit,
    Statistics,
  };
  const switchTabs = (tab) => {
    console.log(tab);
    currentTab.value = tab;
  };
</script>
<style lang="scss" scoped>
  .header {
    position: relative;
    display: flex;
    justify-content: center;
    padding: 10px 20px 50px 20px;
    background-color: var(--main-bg-color-orange);
    color: white;
    font-family: 'Roboto-medium';

    &__settings {
      position: absolute;
      top: 10px;
      right: 20px;
    }
  }
</style>
