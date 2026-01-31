<template>
  <view class="page">
    <view class="title">个人页（模拟）</view>
    <view class="desc">from: {{ from }}</view>

    <nut-button type="primary" @click="back">返回</nut-button>
  </view>
</template>

<script setup>
import Taro from '@tarojs/taro'
import { computed } from 'vue'

const from = computed(() => Taro.getCurrentInstance().router?.params?.from ?? '')

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
</style>
