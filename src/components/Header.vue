<template>
  <div :class="$style.container">
    <div :class="$style.bgImage"></div>
    <span :class="$style.title"><a href="https://zcyblog.tk">ZCY</a> - ToolPage</span>
  </div>
</template>

<script setup>

</script>

<style module>
.container {
  position: relative;
  width: 100%;
  height: 300px;
}

.title {
  position: relative;
  display: inline-block;
  margin: 20px 0 0 40px;
  padding: 20px;
  width: fit-content;
  min-width: 600px;
  z-index: 1;
  color: #fff;
  font-size: 60px;
  text-shadow: 1px 1px #bbb, 2px 2px #bbb, 3px 3px #bbb, 4px 4px #bbb, 5px 5px #bbb, 12px 12px 5px #666;
}

.bgImage {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(to top, antiquewhite, rgba(255, 255, 255, 0)), url(../assets/bg.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position-y: 80%;
  transition: 3s;
}

.container:hover .bgImage {
  transform: scale(1.1);
}
</style>