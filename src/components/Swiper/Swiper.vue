<template>
  <!-- 首页轮播图start -->
  <div class="swiper-container" ref="swiper">
    <div class="swiper-wrapper">
      <slot />
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>
  </div>
  <!-- 首页轮播图ent -->
</template>

<script>
import swiper from 'swiper'
import 'swiper/css/swiper.css'

export default {
  name: 'Swiper',


  props: {
    autoplay: {
      type: Number,
      default: 2000
    },
    loop: {
      type: Boolean,
      default: true
    }
  },
  mounted() {
    // console.log(this.$refs.swiper)  ==> '.swiper-container'
    // 或者还可以是  console.log(this.$el)  ==> '.swiper-container'  ref='swiper'都可以省略掉
    const that = this

    new swiper( this.$refs.swiper, {
      // loop: true, // 循环模式选项

      // 如果需要分页器
      pagination: {
        el: '.swiper-pagination'
      },

      loop: this.loop,

      autoplay: this.autoplay
        ? {
            delay: this.autoplay,
            stopOnLastSlide: false,
            disableOnInteraction: true
          }
        : false,
      on: {
        slideChangeTransitionStart: function() {
          // console.log(this.realIndex)
          that.$emit('change',this.realIndex)
        }
      }
    })
  }
}
</script>
<style lang="scss">
/* 首页轮播图 */
.swiper-container {
  width: 100%;
  height: 180px;
  .swiper-pagination-bullet {
    opacity: 1;
    vertical-align: middle;
    width: 6px;
    height: 6px;
    margin: 0 5px;
    border-radius: 50%;
    background-color: hsla(0, 0%, 100%, 0.7);
  }
  .swiper-pagination-bullet-active {
    width: 20px;
    height:10px;
    margin: 0;
    background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAUBAMAAAANaGKIAAAAMFBMVEUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD8/Pzs7Oyvr68AAADW1tYAAAD///8YAGtvAAAAD3RSTlMABBwyDQgVCyf2zXAQoC3PT9+CAAAAd0lEQVQY02PACQSRAFSIUTS83AUKyksDBcCCojVpSnCQdjwQrDAkqc8YDl6ouQqAFDp1r/wPB7N2qICUimfc/48E/rYVAgVjtP+jgE1HgUaGdaEKrkgVYGAs60QVnJGOXRCrdmwW4XISpuNxeBMzQHAEHWYg4wIAe7Sz99Wx/OUAAAAASUVORK5CYII=)
      no-repeat 50%;
    background-size: contain;
  }
}

/* 首页轮播图end */
</style>