<template>
  <div :class="$style.container" @click="clickHandle">
    <img :class="$style.pic" :src="imgSrc" alt="" />
    <div :class="$style.label">{{ props.config.label }}</div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps(["config"])

const imgSrc = computed(() => "/resources/" + props.config.name + "/" + props.config.pic)
const href = computed(() => "/resources/" + props.config.name + "/" + props.config.index)

function clickHandle() {
  window.open(href.value, "_blank")
}

</script>

<style module>
.container {
  position: relative;
  width: 300px;
  height: 150px;
  margin: 10px;
  border-radius: 5px;
  transition: .3s;
  box-shadow: 3px 3px 3px #aaa;
  cursor: pointer;
  background-color: #fff;
  transition: .3s;
}

.container:hover {
  transform: scale(1.1);
}

.pic {
  position: relative;
  width: 90%;
  height: 90%;
  left: 5%;
  top: 5%;
  filter: opacity(.5);
  object-fit: cover;
  transition: .3s;
}

.label {
  position: absolute;
  width: 100%;
  height: 40px;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
  color: #fff;
  font-size: 18px;
  padding-left: 20px;
  text-shadow: 2px 2px 1px #aaa;
}

.container:hover .pic {
  transform: scale(1.2) rotate(10deg);
}
</style>