<template>
  <view class="index">
    <view class="headline">页面渲染 OK</view>
    <view class="sub">
      如果你能看到这两行文字，说明页面本身渲染正常；接下来验证 NutUI 组件是否可见。
    </view>

    <nut-button type="primary" @click="goDemo">打开 NutUI 演示页</nut-button>
    <nut-button @click="onToast">弹一个 Toast</nut-button>

    <nut-toast v-model:visible="toastVisible" msg="Toast OK" />
  </view>
</template>

<script setup>
import Taro from '@tarojs/taro'
import { onMounted, ref } from 'vue'

const toastVisible = ref(false)

const goDemo = () => {
  Taro.navigateTo({ url: '/pages/demo-nutui/index' })
}

const onToast = () => {
  toastVisible.value = true
}

onMounted(() => {
  // 仅用于快速确认页面脚本是否执行
  console.log('[index] mounted')
})
</script>

<style lang="scss">
.index {
  padding: 24px;
}

.headline {
  font-size: 20px;
  font-weight: 600;
}

.sub {
  margin: 8px 0 16px;
  color: #666;
  font-size: 12px;
}
</style>
