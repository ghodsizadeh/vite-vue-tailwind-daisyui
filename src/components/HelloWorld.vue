<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
</script>

<template>
  <h1 class="text-5xl leading-tight">{{ msg }}</h1>

  <div class="p-8">
    <button
      type="button"
      @click="count++"
      class="rounded-lg border border-transparent px-5 py-2 text-base font-medium bg-neutral-900 text-white transition-colors duration-200 hover:border-indigo-500 focus:outline-none focus:ring-4 focus:ring-indigo-500/40"
    >
      count is {{ count }}
    </button>
    <p class="mt-4 text-sm text-gray-400">
      Edit <code class="font-mono">components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p class="mt-2">
    Check out
    <a
      href="https://vuejs.org/guide/quick-start.html#local"
      target="_blank"
      class="text-indigo-500 hover:text-indigo-400"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p class="mt-2">
    Learn more about IDE Support for Vue in the
    <a
      href="https://vuejs.org/guide/scaling-up/tooling.html#ide-support"
      target="_blank"
      class="text-indigo-500 hover:text-indigo-400"
      >Vue Docs Scaling up Guide</a
    >.
  </p>
  <p class="text-gray-500">Click on the Vite and Vue logos to learn more</p>
</template>

