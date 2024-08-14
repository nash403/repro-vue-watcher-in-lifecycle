<template>
  <div>
    <h2>Hello from CompA</h2>
    <button type="button" @click="count++">
      count++
    </button>
  </div>
</template>

<script setup>
import { nextTick, onMounted, onUnmounted, watch } from 'vue';
import { count } from '../shared'

const initWatcher = () => {
  console.log('initializing watcher in CompA')
  watch(count, () => {
    console.log('Log from watcher of CompA. `count` value is:', count.value)
  })
}

onMounted(async () => {
  console.log('onMounted hook called')
  await Promise.resolve(0)
  initWatcher()
})

onUnmounted(() => {
  console.log('onUnmounted hook called')
})
</script>
