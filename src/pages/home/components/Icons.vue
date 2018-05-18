<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" src="" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconsList: [{
        id: '0001',
        imgUrl: '',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: '',
        desc: '滑雪季'
      }, {
        id: '0003',
        imgUrl: '',
        desc: '泡温泉'
      }, {
        id: '0004',
        imgUrl: '',
        desc: '动植物园'
      }, {
        id: '0005',
        imgUrl: '',
        desc: '景点门票'
      }, {
        id: '0006',
        imgUrl: '',
        desc: '滑雪季'
      }, {
        id: '0007',
        imgUrl: '',
        desc: '泡温泉'
      }, {
        id: '0008',
        imgUrl: '',
        desc: '动植物园'
      }, {
        id: '0009',
        imgUrl: '',
        desc: '全部'
      }]
    }
  },
  computed: {
  // 页码展示区域计算方法:item代表iconsList数组内的每个对象，index代表数组的独立下标
  // page一共会有9个值，8个0和1个1
  // pages[page] = []创建了两个新的数组
  // pages[page].push(item)在第一个和第二个数组中依次添加iconsList数组内的对象
    pages () {
      const pages = []
      this.iconsList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped="scoped">
@import '~styles/variables.styl';
@import '~styles/mixins.styl';
.icons {
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;
  background: green;
  margin-top: .1rem;
}
/*增加能够拖动的Y轴区域*/
.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;
  background: green;
}
.icon {
  position: relative;
  overflow: hidden;
  float: left;
  width: 25%;
  height: 0;
  padding-bottom: 25%;
  background: #25A4BB;
}
.icon-img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: .44rem;
  box-sizing: border-box;
  padding: .1rem;
  background: bisque;
}
.icon-img-content {
  display: block;
  margin: 0 auto;
  height: 100%;
}
.icon-desc {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: .44rem;
  line-height: .44rem;
  text-align: center;
  color: $darkTextColor;
  ellipsis();
}
</style>
