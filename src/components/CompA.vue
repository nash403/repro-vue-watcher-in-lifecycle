<template>
  <div>
    <h2>Hello from CompA</h2>
    <button type="button" @click="count++">
      count++
    </button>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, watch } from 'vue';
import { count } from '../shared'

const initWatcher = () => {
  console.log('initializing watcher in CompA')
  watch(count, () => {
    console.log('Log from watcher of CompA. `count` value is:', count.value)
  })
}

onMounted(async () => {
  console.log('onMounted hook called in CompA')
  await Promise.resolve(0) // this creates the zombie watcher
  // since we are outside the setup scope, Vue can't attach autmatically the vue instance to the watcher
  initWatcher()
})

onUnmounted(() => {
  console.log('onUnmounted hook called in CompA')
})
</script>
