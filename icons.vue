<template>
    <div class="icons">
      <swiper>
        <swiper-slide v-for="(page,index) in pages" :key="index">
          <div class="icon" v-for="item in page" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl">
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
        data(){
          return{
            iconList:[
              {
                id:'0001',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/WX559699/120',
                desc:'景点门票'
              },{
                id:'0002',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/00367748/120',
                desc:'滑雪季'
              },{
                id:'0003',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/WX611179/120',
                desc:'泡温泉'
              },{
                id:'0004',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/00316574/120',
                desc:'动植园'
              },{
                id:'0005',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/WX606587/120',
                desc:'必游榜单'
              },{
                id:'0006',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/WX439101/120',
                desc:'大小洞天'
              },{
                id:'0007',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/00289203/120',
                desc:'自然风光'
              },{
                id:'0008',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/00427680/45',
                desc:'分界洲岛'
              },{
                id:'0009',
                imgUrl:'http://w3.huawei.com/w3lab/rest/yellowpage/face/90006799/45',
                desc:'全部'
              }
            ]
          }
        },
        computed:{
          pages(){    //多页切换
          const pages = []
          this.iconList.forEach((item,index) => {
            const page = Math.floor(index/8)
            if(!pages[page]){
              pages[page] = []
            }
            pages[page].push(item)
          })
          return pages
          }
        }
    }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  @import '~styles/varibles.stylus'
  @import '~styles/mixins.stylus'

  .icons>>> .swiper-container
    height:0
    padding-bottom :50%
    .icon
      position: relative
      float: left
      width :25%
      padding-bottom :25%
      height:0
      .icon-img
        position: absolute
        top:0
        left :0
        right:0
        bottom :.44rem
        box-sizing :border-box
        padding .1rem
        .icon-img-content
          display :block
          height :100%
          margin :0 auto
          margin-top :.1rem
      .icon-desc
        position: absolute
        left :0
        right:0
        bottom :0
        height :.44rem
        line-height .44rem
        color: $darkTextColor
        text-align :center
        ellipse()
</style>
