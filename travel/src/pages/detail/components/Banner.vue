<template>
 <div>
  <div class="banner" @click="handleBannerClick">
    <img :src="bannerImg" class="banner-img">
    <div class="banner-info">
      <div class="banner-title">{{ this.sightName}}</div>
      <div class="banner-number"><span class="iconfont banner-icon">&#xe634;</span>{{this.imgs.length}}</div>
    </div>
  </div>
  <common-fade>
  <common-gallary @close="handleGallaryClose" :imgs="imgs" v-show="showGallary"></common-gallary>
  </common-fade>
 </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import CommonFade from 'common/fade/Fade'

export default {
  name: 'Detail',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array,
  },
  components: {
    CommonGallary,
    CommonFade,
  },
  data () {
    return {
      showGallary:false,
      imgs : ["imgs/recommend1.jpg","imgs/recommend2.jpg","imgs/recommend3.jpg"],
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false

    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position relative
    // 撑开宽高比
    overflow hidden
    height  0
    padding-bottom 55%  
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        height .32rem
        line-height .32rem  
        margin-top .15rem
        padding 0 .4rem
        border-radius .2rem
        background rgba(0,0,0,.8)
        font-size .24rem
        .banner-icon
          font-size .24rem
        

    

</style>