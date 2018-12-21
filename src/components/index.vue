<template>
    <div class="body">

    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide">
                <div class="container">
                    <img src="../../static/source/p_bg.jpg" alt="bg-image" class="bg-image">
                    <div class="title" ></div>
                    <div class="video">
                        <video id="videoid" muted autoplay="autoplay"
                         src="../../static/source/1.mp4" poster="../../static/source/p2_img.jpg" controls="controls"  playsinline="true" webkit-playsinline="true"  preload="auto"></video>
                    </div>
                    <div class="bottom">
                        <div class="bottom-next ani" swiper-animate-effect="fadeInUp" swiper-animate-duration="0.5s" swiper-animate-delay="0.3s"></div>
                        <div class="bottom-text ani" swiper-animate-effect="fadeInUp" swiper-animate-duration="0.6s" swiper-animate-delay="0.4s">向上滑动翻页</div>
                    </div>
                </div>
            </div>
            <div class="swiper-slide">
                 <div classs="container">
                    <div class="title2"></div>
                    <div class="gif-img ani" swiper-animate-effect="bounceInLeft" swiper-animate-duration="0.5s" swiper-animate-delay="0.2s">
                        <img src="../../static/source/p2.gif" alt="">
                    </div>
                     <div class="gif-img ani" swiper-animate-effect="slideInUp" swiper-animate-duration="1.5s" swiper-animate-delay="0.7s">
                        <img src="../../static/source/p2_text.jpg" alt="">
                    </div>
                 </div>
            </div>
            <div class="swiper-slide">
                <div class="container">
                    <div class="title2"></div>
                    <div class="gif-img ani" swiper-animate-effect="rotateInUpRight" swiper-animate-duration="0.3s" swiper-animate-delay="0.2s">
                        <img src="../../static/source/p3.gif" alt="">
                    </div>
                     <div class="gif-img ani" swiper-animate-effect="rotateInDownLeft" swiper-animate-duration="1.5s" swiper-animate-delay="0.7s">
                        <img src="../../static/source/p3_text.jpg" alt="">
                    </div>
                 </div>
            </div>
             <div class="swiper-slide">
                <div class="container">
                    <div class="title2"></div>
                    <div class="gif-img ani" swiper-animate-effect="rotateInUpRight" swiper-animate-duration="0.3s" swiper-animate-delay="0.2s">
                        <img src="../../static/source/p4.gif" alt="">
                    </div>
                     <div class="gif-img ani" swiper-animate-effect="lightSpeedIn" swiper-animate-duration="2.3s" swiper-animate-delay="0.7s">
                        <img src="../../static/source/p4_text.jpg" alt="">
                    </div>
                 </div>
            </div>
             <div class="swiper-slide">
                <div class="container">
                     <img src="../../static/source/p5_bg.jpg" alt="bg-image" class="bg-image">
                     <div class="title title2" style="top:0;left:1.6rem"></div>
                     <div class="gif-img-ab ani" swiper-animate-effect="fadeIn" swiper-animate-duration="1.3s" swiper-animate-delay="0.3s">
                         <img src="../../static/source/p5.gif" alt="gif" class="ani" swiper-animate-effect="fadeInRightBig" swiper-animate-duration="1.3s" swiper-animate-delay="0.5s">
                         <img src="../../static/source/p5_text.png" alt="text" class="ani" swiper-animate-effect="rotateInUpLeft" swiper-animate-duration="2.3s" swiper-animate-delay="1.5s">
                     </div>
                 </div>
            </div>
        </div>

    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Swiper from 'swiper'
import swiper from 'script-loader!@/assets/swiper.min.js'
import animate from 'script-loader!@/assets/swiper.animate.min.js'

export default {
  name : "index",
  mounted:function (){
     this.initFun(750,1206);
     new Swiper ('.swiper-container', {
        direction:"vertical",
        on:{
            init: function(){
                swiperAnimateCache(this); //隐藏动画元素 
                swiperAnimate(this); //初始化完成开始动画
            }, 
            slideChangeTransitionEnd: function(){ 
                swiperAnimate(this); //每个slide切换结束时也运行当前slide动画
                //this.slides.eq(this.activeIndex).find('.ani').removeClass('ani'); 动画只展现一次，去除ani类名
            } 
        }
     })     
     document.getElementById("videoid").play();  
  },
  methods: {
    initFun:function(designW, designH) {
          var prevScreenW = null;
          function resize() {
            var screenW = window.innerWidth;
            var screenH = window.innerHeight;
            if (screenW / screenH > designW / designH) { // 矮胖屏幕
              document.documentElement.style.fontSize = 100 * screenH / designH + "px"
            } else { // 高瘦屏幕
              document.documentElement.style.fontSize = 100 * screenW / designW + "px"
            }
          }
          window.onload = window.onresize = resize
          resize();
         

        },  
  }
}
</script>

<style scoped>

 .body { 
        position: fixed;
        top: 50%;
        left: 50%;
        z-index: 10;
        transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);
        -moz-transform: translate(-50%, -50%);
        -webkit-transform: translate(-50%, -50%);
        -o-transform: translate(-50%, -50%);
        overflow: auto;
        width: 7.5rem;
        height: 12.06rem;
        overflow: hidden;
      }
  .swiper-container {
        width: 100%;
        height: 100%;
  }
  .container {
    width: 100%;
    height: 100%;
    position: relative;
    overflow: hidden;
  }
  .bg-image {
      width: 100%;
  }
  .title{
        width: 5.23rem;
        height: .93rem;
        position: absolute;
        left: 50%;
        top: 2.4rem;
        transform: translateX(-50%);
        background-image: url("../../static/source/p0_logo.png");
        background-repeat: no-repeat;
        background-size: cover;
        box-sizing: border-box;
  }
  .video{
        width: 7.23rem;
        /* height: .93rem; */
        position: absolute;
        left: 50%;
        top: 4.4rem;
        transform: translateX(-50%);
        /* background-image: url("../../static/source/p0_logo.png"); */
        background-repeat: no-repeat;
        background-size: cover;
        box-sizing: border-box;
  }
  .video video{
      width: 100%;
      height: 100%;
  }
  .bottom{
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 1.8rem;
    display: flex;
    -ms-flex-direction: column;
    flex-direction: column;
    padding-bottom: .6rem;
    -ms-flex-align: center;
    align-items: center;
    -ms-flex-pack: end;
    justify-content: flex-end;
  }
  .bottom-next{
     width: .6rem;
     height: .6rem;
     background-image: url("../../static/source/finger.png");
     background-repeat: no-repeat;
     background-size: cover;
     box-sizing: border-box;
  }
  .title2{
      /* position: absolute; */
      left: .6rem;
      top: .6rem;
      width: 3.28rem;
      height: .94rem;
      margin: 10px;
      background-image: url("../../static/source/p1_title.png");
      background-repeat: no-repeat;
      background-size: contain;
      box-sizing: border-box;
  }
  .gif-img{
      width: 100%;
  }
  .gif-img-ab{
      position:absolute;
      z-index: 100;
      top:4.3em;
      background: #fff;
      padding: 10px;
      margin:10px;
  }
  .gif-img-ab img{
      width: 100%;
  }
   .gif-img img{
       width: 100%;
   }
  .an-img{
    transition:  2s;
    -webkit-transition:  2s; /* Safari */
   }
</style>

