<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">{{ title }}</text>
    </view>
    <button @click="changeToken">btn {{ token }}</button>
  </view>
</template>

<script setup lang="ts">
import { useUserStore } from '@/stores/user';
import { ref } from 'vue'
const title = ref('Hello')
const store=useUserStore()
const {token} =storeToRefs(store)

const changeToken=()=>{
  store.token='xysccc'
  uni.navigateTo({url:'/pages/test/index'})
}
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .logo {
  height: 200rpx;
  width: 210rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
