<template>
  <section>
    <button
      v-for="(_, tab) in tabs"
      :key="tab"
      class="tab"
      @click="$emit('click', tab)"
    >
      {{ tab }}
    </button>
  </section>
</template>
<script setup>
  defineProps(['tabs', 'currentTab']);
  defineEmits(['switchTab']);
</script>
<style lang="scss" scoped></style>
