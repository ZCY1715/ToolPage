<template>
  <div :class="$style.container">
    <div :class="$style.wrap">
      <ToolBox v-for="toolWebSite of config" :config="toolWebSite" />
    </div>
    <div :class="$style.mask"></div>
  </div>
</template>

<script setup>
import ToolBox from './ToolBox.vue'
import { ref, onMounted } from 'vue'

const config = ref([])

onMounted(async () => {
  const res = await fetch("/resources/config.json")
  config.value = await res.json()
})

</script>

<style module>
.container {
  position: relative;
  width: 100%;
  flex: 1;
  background-color: antiquewhite;
  overflow-x: hidden;
  overflow-y: visible;
}

.container::-webkit-scrollbar {
  display: none;
}

.wrap {
  position: relative;
  padding-top: 20px;
  width: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fit, 320px);
  row-gap: 30px;
  column-gap: 20px;
  justify-content: space-evenly;
}

.mask {
  position: fixed;
  width: 100%;
  height: calc(100vh - 300px);
  left: 0;
  top: 300px;
  pointer-events: none;
  background: linear-gradient(to top, transparent 0%, transparent 85%, antiquewhite 100%);
}
</style>