<template>
  <view class="wrap">
    <view
      class="tab-item"
      v-for="(item, index) in dataList"
      :key="index"
      @click="onSwitchTabClick"
    >
      {{ item.name }}
    </view>
    <view class="active-bar-wrap" :animation="animationData" :style="{ width: activeBarStyle.width }">
      <view class="active-bar"></view>
    </view>
  </view>
</template>

<script>
export default {
  name: "switchTab",
  props: {
    dataList: {
      type: Array,
      default: [],
    },
  },
  data() {
    return {
      activeBarStyle: {
        left: "0",
        width: "0",
      },
      animation: null,
      animationData: null
    };
  },
  computed: {},
  methods: {
    initBar() {
      const { screenWidth } = wx.getSystemInfoSync();
      this.activeBarStyle.width = screenWidth / this.dataList.length + "px";
      this.animation = uni.createAnimation({
        duration: 700,
        timingFunction: 'ease'
      });
    },
    onSwitchTabClick(event) {
      const left = event.currentTarget.offsetLeft;
      const animation = this.animation;
      console.log("left :>> ", left);
      animation.left(left).step()
      this.animationData = animation.export();
    }
  },
  watch: {},

  // 组件周期函数--监听组件挂载完毕
  mounted() {
    this.initBar();
  },
  // 组件周期函数--监听组件数据更新之前
  beforeUpdate() {},
  // 组件周期函数--监听组件数据更新之后
  updated() {},
  // 组件周期函数--监听组件激活(显示)
  activated() {},
  // 组件周期函数--监听组件停用(隐藏)
  deactivated() {},
  // 组件周期函数--监听组件销毁之前
  beforeDestroy() {},
};
</script>

<style lang="less" scoped>
.wrap {
  position: relative;
  display: flex;
  align-items: center;

  .tab-item {
    font-size: 32upx;
    color: #383838;
    text-align: center;
    flex: 1;
    z-index: 10;
  }

  .active-bar-wrap {
    position: absolute;
    left: 0;
    bottom: -6upx;

    .active-bar {
      width: 50%;
      height: 30upx;
      background: #29ffd0;
      border-radius: 12upx;
      margin: 0 auto;
    }
  }
}
</style>