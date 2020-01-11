<template>
	<div class="swiper">
    <swiper :options="swiperOption" v-if="isShow">
    <!-- slides -->
    <swiper-slide v-for="(item,index) in swiperList" :key="index">
  
    	<img class="swiper-img" :src="item.imgUrl" alt="">
    	
    </swiper-slide>
    
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>

	</div>
</template>

<script>
	export default {
		name  : 'HomeSwiper',
		props : ['swiperList'],
		data(){
			return{
				swiperOption: {
					pagination: {
			            el: '.swiper-pagination'
        		},
        		 loop:true,
        		 autoplay:true
			}
		}
      
    },
        computed:{
          isShow(){
            return this.swiperList.length>0
          }
        }
    }
</script>


<style lang="less" scoped>
	.swiper{
		heigth:2.19rem;
		.swiper-container {
			height:100%;
			.swiper-img{
				width:100%;
			}
		}
	}

</style>