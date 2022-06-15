<template>
  <ul class="superset__exercises">
    <li class="superset__exercise" v-for="(superset, i) in supersets" :key="i">
      {{ superset.name }}
    </li>
  </ul>
</template>
<script setup>
  import { ref } from 'vue';
  import supersetsLookup from '../../exercises/superset.lookup.js';

  const supersets = ref(supersetsLookup);
</script>
<style lang="scss" scoped>
  .superset__exercises {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
  }
  .superset__exercise {
    cursor: pointer;
    color: var(--main-bg-color-orange);
  }
</style>
