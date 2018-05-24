<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png" />
      <div class="banner-info">
        <div class="banner-title">
                          大连圣亚海洋世(AAAA景区)
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63b;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-show="showGallary"
      @close="handleGallaryClose"
    ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg', 'http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
}
.banner img {
  width: 100%;
}
.banner-info {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  line-height: .6rem;
  display: flex;
  background-image: linear-gradient(top, rgba(0,0,0,0),rgba(0,0,0,0.8));
}
.banner-title {
  flex: 1;
  font-size: .32rem;
  padding: 0 .2rem;
  color: #fff;
}
.banner-number {
  padding: 0 .4rem;
  height: .32rem;
  line-height: .32rem;
  border-radius: .2rem;
  margin-top: .14rem;
  margin-right: .1rem;
  background-color: rgba(0,0,0, .8);
  font-size: .24rem;
  color: #fff;
}
.banner-icon {
  font-size: .24rem;
}
</style>
