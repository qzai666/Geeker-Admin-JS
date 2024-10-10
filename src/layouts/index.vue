<!-- 💥 这里是一次性加载 LayoutComponents -->
<template>
  <el-watermark id="watermark" :font="font" :content="watermark ? ['Geeker Admin', 'Happy Working'] : ''">
    <LayoutVertical />
    <ThemeDrawer />
  </el-watermark>
</template>

<script setup name="layout">
import { computed, reactive, watch } from 'vue'
import ThemeDrawer from './components/ThemeDrawer/index.vue'
import LayoutVertical from './LayoutVertical/index.vue'
import { useGlobalStore } from '@/stores/modules/global.js'

const globalStore = useGlobalStore()
const watermark = computed(() => globalStore.watermark)
const font = reactive({ color: 'rgba(0, 0, 0, .15)' })
</script>

<style scoped lang="scss">
.layout {
  min-width: 600px;
}
</style>
