<template>
  <ul class="strenght__exercises">
    <li class="strenght__exercise" v-for="(ex, i) in exercises">
      {{ ex.name }}
    </li>
  </ul>
</template>
<script setup>
  import { ref } from 'vue';
  import exercisesLookup from '../../exercises/exercises.lookup.js';

  const exercises = ref(exercisesLookup);
</script>
<style lang="scss" scoped>
  .strenght__exercises {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
  }
  .strenght__exercise {
    cursor: pointer;
    color: var(--main-bg-color-orange);
  }
</style>
