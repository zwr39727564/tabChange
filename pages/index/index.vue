<template>
  <view class="wrap">
    <view class="item" @click="goDemo1">
      普通tab切换(demo1)
    </view>
    <view class="item" @click="goDemo2">
      swiper + scroll-view(demo2)
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  },
  onLoad() {},
  methods: {
    goDemo1() {
      uni.navigateTo({ url: '/pages/demo1/demo1' });
    },
    goDemo2() {
      uni.navigateTo({ url: '/pages/demo2/demo2' });
    }
  },
};
</script>

<style lang="less" scoped>

.wrap {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;

  .item {
    width: 80%;
    font-size: #000;
    line-height: 100upx;
    text-align: center;
    border-radius: 4px;
    border: 1px solid #000;
    margin-bottom: 50upx;

    &:last-child {
      margin-bottom: 0;
    }
  }
}

</style>
