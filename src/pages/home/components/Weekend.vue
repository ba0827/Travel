<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" src="" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: '',
        title: '海洋世界',
        desc: '浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园'
      }, {
        id: '0002',
        imgUrl: '',
        title: '海洋世界',
        desc: '浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园'
      }, {
        id: '0003',
        imgUrl: '',
        title: '海洋世界',
        desc: '浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园浪漫的海洋世界公园'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped="scoped">
@import '~styles/mixins.styl';
.title {
  margin-top: .2rem;
  line-height: .8rem;
  background: #ccc;
  text-indent: .2rem;
}
.item-img-wrapper {
  height: 0;
  overflow: hidden;
  padding-bottom: 33.9%;
}
.item-img {
  width: 100%;
  height: 2.8rem;
  background: #25A4BB;
}
.item-info {
  padding: .1rem;
}
.item-title {
  line-height: .54rem;
  font-size: .32rem;
  ellipsis();
}
.item-desc {
  line-height: .4rem;
  color: darkred;
  ellipsis();
}
</style>
