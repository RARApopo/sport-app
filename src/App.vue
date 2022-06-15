<template>
  <header class="header">
    <div class="header__inner container">
      <div class="header__logo">Sportsman</div>
      <button class="header__settings">Settings</button>
      <span class="header__subtitle">{{ currentTab }}</span>
    </div>
    <Tabs
      class="tabs"
      :tabs="tabs"
      :current-tab="currentTab"
      @switchTabs="switchTabs"
    />
  </header>

  <main class="main">
    <component :is="tabs[currentTab]"></component>
  </main>

  <footer class="footer">
    <div class="container">Made by Romanza Zaritskyi</div>
  </footer>
</template>
<script setup>
  import Tabs from './components/tabs/tabs.vue';
  import { ref } from 'vue';

  import Strength from './components/main-pages/strength.vue';
  import Supersets from './components/main-pages/supersets.vue';
  import Statistics from './components/main-pages/statistics.vue';
  // Tabs logic need to write in tabs.vue
  const currentTab = ref('Strength');
  const tabs = {
    Strength,
    Supersets,
    Statistics,
  };
  const switchTabs = (tab) => {
    currentTab.value = tab;
  };
  // Tabs logic need to write in tabs.vue
</script>
<style lang="scss" scoped>
  .header {
    position: sticky;
    top: 0;
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 10px 0px;
    background-color: var(--main-bg-color-orange);
    color: white;
    font-family: 'Roboto-medium';

    &__inner {
      display: grid;
      grid-template-rows: 1fr 1fr;
      justify-items: center;
    }

    &__subtitle {
      color: black;
      font-family: 'Roboto-light';
      font-size: 12px;
    }

    &__settings {
      position: absolute;
      top: 10px;
      right: 20px;
      background-color: transparent;
      color: inherit;
      transition: all 0.2s linear;
      cursor: pointer;

      &:hover {
        color: blue;
      }
    }
  }

  .footer {
    position: fixed;
    bottom: 0;
    width: 100%;
    padding: 12px 0px;
    background-color: var(--main-bg-color-orange);
    color: white;
  }
</style>
