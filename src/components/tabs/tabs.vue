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
