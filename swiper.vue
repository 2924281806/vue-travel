<template>
    <div class="swiper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeSwiper',
        data(){
          return{
            swiperOption:{
              pagination:'.swiper-pagination',
              loop:true
            },
            swiperList:[{
              id:'0001',
              imgUrl:'http://image.huawei.com/tiny-lts/v1/images/a8473258156b9525275e_780x250.jpg'
            },{
              id:'0002',
              imgUrl:'http://image.huawei.com/tiny-lts/v1/images/b271e257f9d528797ed2_780x250.png'
            },{
              id:'0003',
              imgUrl:'http://image.huawei.com/tiny-lts/v1/images/50807257e253cf78b0bc_780x250.jpg'
            }]
          }
        }
    }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .swiper>>> .swiper-pagination-bullet-active
    background :#fff
  .swiper
    overflow :hidden
    width :100%
    height:0
    padding-bottom :32%
    background :#eee
    .swiper-img
      width:100%
</style>
