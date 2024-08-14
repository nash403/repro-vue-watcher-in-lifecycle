<script setup>
import { ref } from 'vue'
import CompA from './components/CompA.vue';
import CompB from './components/CompB.vue';
import { count } from './shared';

const toggleShowCompA = ref(true);
</script>

<template>
  <main>
    <p>Click button to toggle between CompA / CompB components</p>
    <button type="button" @click="toggleShowCompA = !toggleShowCompA">
      Toggle
    </button>

    <div class="wrapper">
      <CompA v-if="toggleShowCompA" />
      <CompB v-else />
    </div>

    <pre>count value is {{ count }}</pre>
  </main>
</template>

<style scoped>
.wrapper {
  margin-top: 1em;
  padding: 1em;
  background-color: #888;
}
</style>
