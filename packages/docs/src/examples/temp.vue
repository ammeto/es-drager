<template>
  <button @click="snap = !snap">切换snap</button>
  <button @click="add">添加</button>
  <div style="position: relative;width: 500px;height: 500px;background-color: #ccc;">
    <Drager v-for="item in list" :key="item.left + item.top" :width="item.width" :height="item.height" :left="item.left" :top="item.top" :snap="snap" :markline="snap">
    </Drager>
  </div>

</template>

<script setup lang="ts">
import { ref } from 'vue'
import Drager from 'es-drager/index'
const snap = ref(false)
const list = ref([
  {
    width: 100,
    height: 100,
    left: 100,
    top: 100,
  },
  {
    width: 100,
    height: 100,
    left: 200,
    top: 200,
  }
])

function add() {
  list.value.push({
    width: 100,
    height: 100,
    left: 200,
    top: 200,
  })
}
</script>

<style>
.es-drager-dot {
  z-index: 100;
}
</style>