<template>
  <view class="page">
    <view class="title">NutUI + Taro (Vue3)</view>
    <view class="desc">用于验证 NutUI 组件与样式是否生效</view>

    <nut-button type="primary" @click="onToast">点我弹 Toast</nut-button>

    <view class="spacer" />

    <nut-button @click="goRouter">去路由演示页</nut-button>
    <nut-button @click="goProfile">去个人页</nut-button>

    <nut-toast v-model:visible="toastVisible" msg="NutUI Toast OK" />
  </view>
</template>

<script setup>
import Taro from '@tarojs/taro'
import { ref } from 'vue'

const toastVisible = ref(false)

const onToast = () => {
  toastVisible.value = true
}

const goRouter = () => {
  Taro.navigateTo({ url: '/pages/demo-router/index' })
}

const goProfile = () => {
  Taro.navigateTo({ url: '/pages/mock-profile/index?from=demo-nutui' })
}
</script>

<style lang="scss">
.page {
  padding: 24px;
}

.title {
  font-size: 20px;
  font-weight: 600;
}

.desc {
  margin-top: 8px;
  color: #666;
  font-size: 12px;
}

.spacer {
  height: 16px;
}
</style>
