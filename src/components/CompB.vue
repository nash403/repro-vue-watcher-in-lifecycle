<template>
  <div>
    <h2>Hello from CompB</h2>
    <button type="button" @click="count++">
      count++
    </button>
  </div>
</template>

<script setup>
import { count } from '../shared'
</script>
