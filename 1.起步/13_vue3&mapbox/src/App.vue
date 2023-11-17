<template>
  <div id="container">
  </div>
</template>

<script setup lang="ts">
import mapboxGl from 'mapbox-gl'
import { onMounted } from 'vue'
// 获取token
mapboxGl.accessToken = import.meta.env.VITE_TOKEN

// 进行地图配置
onMounted(()=>{
  const map = new mapboxGl.Map({
    container: 'container', // 容器id
    style: 'mapbox://styles/mapbox/streets-v12', // 样式
    center: [116.395645, 39.92998], // 中心点
    zoom: 12 // 缩放级别
  })
  map.addControl(new mapboxGl.NavigationControl())
})
</script>

<style lang="scss" scoped>
#container{
  position: absolute;
  height: 100%;
  width: 100%;
}
</style>
