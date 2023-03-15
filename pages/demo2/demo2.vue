<template>
  <div class="wrap">
    <switch-tab
      :dataList="dataList"
      :currentTab="currentIndex"
      @changeSwiper="switchSwiper"
    ></switch-tab>
    <swiper :current="currentIndex" @change="handleSwiper">
      <swiper-item>
        <scroll-view scroll-y>
          <view class="list">
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
            <view class="item"> 酒店1 </view>
          </view>
        </scroll-view>
      </swiper-item>
      <swiper-item>
        <scroll-view scroll-y>
          <view class="list">
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
            <view class="item"> 餐厅1 </view>
          </view>
        </scroll-view>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
import switchTab from "../../components/switchTab2/switchTab2";

export default {
  components: {
    switchTab,
  },
  data() {
    return {
      title: "demo2",
      dataList: [
        {
          id: "0",
          name: "酒店",
        },
        {
          id: "1",
          name: "餐厅",
        },
      ],
      currentIndex: 0,
    };
  },
  computed: {},
  methods: {
    handleSwiper(e) {
      const { current } = e.detail;
      console.log("current :>> ", current);
      this.currentIndex = current;
    },
    switchSwiper(e) {
      console.log("switchSwiper");
      console.log("e :>> ", e);
      this.currentIndex = e.current;
    }
  },
  watch: {},

  // 页面周期函数--监听页面加载
  onLoad() {},
  // 页面周期函数--监听页面初次渲染完成
  onReady() {},
  // 页面周期函数--监听页面显示(not-nvue)
  onShow() {},
  // 页面周期函数--监听页面隐藏
  onHide() {},
  // 页面周期函数--监听页面卸载
  onUnload() {},
  // 页面处理函数--监听用户下拉动作
  // onPullDownRefresh() { uni.stopPullDownRefresh(); },
  // 页面处理函数--监听用户上拉触底
  // onReachBottom() {},
  // 页面处理函数--监听页面滚动(not-nvue)
  // onPageScroll(event) {},
  // 页面处理函数--用户点击右上角分享
  // onShareAppMessage(options) {},
};
</script>

<style lang="less" scoped>
.wrap {
  padding-top: 50upx;

  swiper {
    width: 100%;

    scroll-view {
      height: calc(100vh);

      .list {
        width: 100%;

        .item {
          font-size: 32upx;
          line-height: 50upx;
          color: #000;
        }
      }
    }
  }
}
</style>