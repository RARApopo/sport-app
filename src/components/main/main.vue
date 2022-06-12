<template>
  <header class="header">
    <span class="header__logo">Sportsman</span>
    <button class="header__settings">Settings</button>
  </header>
  <Tabs :tabs="tabs" :current-tab="currentTab" @switchTabs="switchTabs" />

  <component :is="tabs[currentTab]"></component>

  <footer class="footer">Some footer heare</footer>
</template>
<script setup>
  import Tabs from '../tabs/tabs.vue';
  import { ref } from 'vue';

  import Strength from '../main-pages/strength.vue';
  import Circuit from '../main-pages/circuit.vue';
  import Statistics from '../main-pages/statistics.vue';

  // Tabs logic need to write in tabs.vue
  const currentTab = ref('Strength');
  const tabs = {
    Strength,
    Circuit,
    Statistics,
  };
  const switchTabs = (tab) => {
    currentTab.value = tab;
  };
  // Tabs logic need to write in tabs.vue
</script>
<style lang="scss" scoped>
  .header {
    position: relative;
    display: flex;
    justify-content: center;
    padding: 10px 20px 10px 20px;
    background-color: var(--main-bg-color-orange);
    color: white;
    font-family: 'Roboto-medium';

    &__settings {
      position: absolute;
      top: 10px;
      right: 20px;

      background-color: transparent;
      border: none;
      color: inherit;

      cursor: pointer;
      transition: all 0.2s linear;
      &:hover {
        color: blue;
      }
    }
  }

  .footer {
    position: fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 40px;
    background-color: var(--main-bg-color-orange);
    color: white;
  }
</style>
