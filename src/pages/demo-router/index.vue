<template>
  <view class="page">
    <view class="title">Taro 路由演示（weapp）</view>
    <view class="desc">
      - navigateTo/redirectTo/navigateBack
    </view>

    <nut-button type="primary" @click="goProfile">navigateTo 个人页（带参数）</nut-button>

    <view class="spacer" />

    <nut-button @click="redirectToNutui">redirectTo NutUI 演示页</nut-button>
    <nut-button @click="back">navigateBack</nut-button>
  </view>
</template>

<script setup>
import Taro from '@tarojs/taro'

const goProfile = () => {
  Taro.navigateTo({ url: '/pages/mock-profile/index?from=demo-router' })
}

const redirectToNutui = () => {
  Taro.redirectTo({ url: '/pages/demo-nutui/index' })
}

const back = () => {
  Taro.navigateBack({ delta: 1 })
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
  margin: 8px 0 16px;
  color: #666;
  font-size: 12px;
}

.spacer {
  height: 16px;
}
</style>
