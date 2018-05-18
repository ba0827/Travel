<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/c4/1cdd28811593b802.jpg_750x200_5fbb7c91.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/c4/1cdd28811593b802.jpg_750x200_5fbb7c91.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped="scoped">
/*>>>样式穿透*/
.wrapper >>> .swiper-pagination-bullet-active {
  background: #fff;
}
/*让元素的宽高比始终为31，这是为了解决网速过慢时页面抖动问题，设置height不行的*/
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 31%;
}

.swiper-img {
  width: 100%;
}
</style>
