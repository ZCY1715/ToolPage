<template>
  <div :class="$style.container">
    <Header />
    <ToolContainer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import ToolContainer from './components/ToolContainer.vue'

</script>

<style module>
.container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
</style>
