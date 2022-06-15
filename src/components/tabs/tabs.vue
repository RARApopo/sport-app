<template>
  <section class="tabs">
    <div class="container">
      <div class="tabs__inner">
        <button
          v-for="(_, tab) in tabs"
          :key="tab"
          class="tab"
          @click="$emit('switchTabs', tab)"
        >
          {{ tab }}
        </button>
      </div>
    </div>
  </section>
</template>
<script setup>
  defineProps(['tabs', 'currentTab']);
  defineEmits(['switchTabs']);
</script>
<style lang="scss" scoped>
  .tabs {
    background-color: var(--main-bg-color-orange);
    &__inner {
      display: flex;
      justify-content: space-between;
    }
  }

  .tab {
    position: relative;
    background-color: transparent;
    border: none;
    color: white;
    cursor: pointer;
    transition: all 0.2s linear;

    &:focus::after {
      content: '';
      position: absolute;
      top: 26px;
      display: block;
      width: 100%;
      height: 4px;
      background-color: white;
    }
  }
</style>
