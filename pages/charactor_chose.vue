<template>
  <div class="container">
    <div class="title">
      <p>キャラクター選択</p>
    </div>
    <Character />
  </div>

  
</template>

<script setup>
import Character from "../components/Character.vue"

import { ref } from 'vue'
import { useDraggable } from '@vueuse/core'

const el = ref<HTMLElement | null>(null)

// `style` will be a helper computed for `left: ?px; top: ?px;`
const { x, y, style } = useDraggable(el, {
  initialValue: { x: 40, y: 40 },
})
</script>

<style scoped>
.container {
  height: 100%;
}

.title {
  text-align: center;
  font-size: 70px;
}


</style>
