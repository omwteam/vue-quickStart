<template>
    <swiper :options="swiperOption" ref="mySwiperA">
      <!-- 幻灯内容 -->
      <swiper-slide><img src="../assets/kw-banner1.png" alt="" width="100%"></swiper-slide>
      <swiper-slide><img src="../assets/kw-banner2.png" alt="" width="100%"></swiper-slide>
      <!--<swiper-slide><img src="../assets/kw-banner1.png" alt="" width="100%"></swiper-slide>-->
      <!--<swiper-slide><img src="../assets/kw-banner2.png" alt="" width="100%"></swiper-slide>-->
      <!-- ... -->
      <!-- 以下控件元素均为可选（使用具名slot来确定并应用一些操作控件元素） -->
      <!--<div class="swiper-pagination"  slot="pagination"></div>-->
      <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
      <!--<div class="swiper-button-next" slot="button-next"></div>-->
      <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
    </swiper>



</template>

<script>
  import { swiper, swiperSlide, swiperPlugins } from 'vue-awesome-swiper'

  export default {
    name: "swipe",
    components: {
      swiper,
      swiperSlide
    },
    data () {
      return {
        swiperOption: {
          // 所有配置均为可选（同Swiper配置）
          // NotNextTick is a component's own property, and if notNextTick is set to true, the component will not instantiate the swiper through NextTick, which means you can get the swiper object the first time (if you need to use the get swiper object to do what Things, then this property must be true)
          // notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象（假如你需要使用获取swiper对象来做什么事，那么这个属性一定要是true）
//          notNextTick: true,
//          autoplay: 3000,
////          direction : 'vertical',
//          grabCursor : true,
//          setWrapperSize :true,
//          autoHeight: true,
//          pagination : '.swiper-pagination',
//          paginationClickable :true,
//          prevButton:'.swiper-button-prev',
//          nextButton:'.swiper-button-next',
//          scrollbar:'.swiper-scrollbar',
//          mousewheelControl : true,
//          observeParents:true,
//          // if you need use plugins in the swiper, you can config in here like this
//          // 如果自行设计了插件，那么插件的一些配置相关参数，也应该出现在这个对象中，如下debugger
//          debugger: false,
//          // swiper callbacks
//          // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
//          onTransitionStart(swiper){
//            console.log(swiper)
//          },
          // more Swiper config ...
          // ...
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

