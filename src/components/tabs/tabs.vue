<template>
  <section class="tabs">
    <button
      v-for="(_, tab) in tabs"
      :key="tab"
      class="tab"
      @click="$emit('switchTabs', tab)"
    >
      {{ tab }}
    </button>
  </section>
</template>
<script setup>
  defineProps(['tabs', 'currentTab']);
  defineEmits(['switchTabs']);
</script>
<style lang="scss" scoped>
  .tabs {
    background-color: var(--main-bg-color-orange);
    display: flex;
    justify-content: space-around;
  }

  .tab {
    background-color: transparent;
    border: none;
    color: white;
    cursor: pointer;
    transition: all 0.2s linear;
    &:hover {
      color: blue;
    }
  }
</style>
