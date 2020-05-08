<template>
  <div class="home">
    <!-- 头部start -->
    <header class="index-header">
      <a href="mine.html?cpid=0">
        <div class="header-user">
          <div class="user-btn"></div>
        </div>
      </a>
      <div class="header-logo"></div>
      <a href="search.html?cpid=0">
        <div class="header-search"></div>
      </a>
    </header>
    <!-- 头部ent -->
    <br />
    <br />
    <!-- 首页轮播图start -->
    <Swiper class="my-swiper" @change="Onchange">
      <SwiperItem>
        <img
          src="https://img.manhuadao.cn/upload/AdGroup201906/9315f7dd68b346928219f29bd9c89e60.jpg"
          alt
        />
      </SwiperItem>
      <SwiperItem>
        <img
          src="https://img.manhuadao.cn/upload/AdGroup201903/22b43c03a0f943cda001c5338fe0ddd9.jpg"
          alt
        />
      </SwiperItem>
      <SwiperItem>
        <img
          src="https://img.manhuadao.cn/upload/AdGroup202003/dda50e4233e34186910fd490aea1cd91.jpg"
          alt
        />
      </SwiperItem>
    </Swiper>

    <!-- 首页轮播图ent -->
  </div>
</template>


<script>
import Swiper from '@/components/Swiper/Swiper.vue'
import SwiperItem from '@/components/Swiper/SwiperItem.vue'

//{}这种形式 的引人新建一个index.js 文件 在其里进行引人操作
// import{Swiper,SwiperItem} from '@/components/Swiper'

export default {
  name: 'home',
  components: {
    Swiper,
    SwiperItem
  },
  methods: {
    Onchange(index) {
      console.log('hello', index)
    }
  }
}
</script>
<style scoped lang="scss">
/* mixins里的引人是@import; */
/* @import '../../assets/styles/mixins.scss'; */
/* 在style里用@的时候要加~@ */
@import '~@/assets/styles/mixins.scss';
.home {
  display: flex;
  flex-flow: column;
  height: 100%;
  background: chartreuse;

  /* 首页头部 */
  .index-header {

    display: flex;
    height: 44px;
    justify-content: space-between;
    align-items: center;
    background: burlywood;
    padding: 0 10px;
    /* border-bottom: 1px solid red; */
    /* 见mixins.scss */
    @include border-bottom;
    }
    /* 头部用户图标 */
    .user-btn {
      width: 25px;
      height: 25px;
      background: url('../../assets/icon/user-btn.png') no-repeat;
      background-size: 100%;
    }
    /* 头部logo图标 */
    .header-logo {
      width: 94px;
      height: 28px;
      background: url('../../assets/logo.png');
      background-size: 100%;
    }

    /* 头部搜索图标 */
    .header-search {
      width: 25px;
      height: 25px;
      background: url('../../assets/icon/search.png');
      background-size: 100%;
    }
  }
  /* 首页头部end */

  .my-swiper {
    width: 100%;
    img {
      width: 375px;
      height: 180px;
    }
  }

</style>

