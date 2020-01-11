<template>
	<swiper  :options="swiperOption">
		<swiper-slide v-for="(imgs , index) in filterImgs" :key="index">
			<div class="nav">
				<div class="item" v-for="item in imgs">
					<img class="item-img" :src="item.imgUrl" alt="">
					<span class="item-desc">{{item.desc}}</span>
				</div>
			</div>
		</swiper-slide>
	    <div class="swiper-pagination" slot="pagination"></div>
	</swiper>
</template>
<script>
 export default {
		name : 'Nav',
		props : ['imgsList'],
		data() {
          return{
            swiperOption:{
              pagination: {
                el: '.swiper-pagination'
              }
            }
         }
       },
       computed:{
       	  filterImgs(){
       	  	let imgs = [];
       	  	this.imgsList.forEach((item,index) => {
       	  		let page = ~~(index/8) //~~qu zheng
       	  		if(!imgs[page]){  //如果page等于0; 取反则为true
       	  			imgs[page] = []
       	  		}
       	  		imgs[page].push(item)
       	  	})
       	  	return imgs;
       	  }
       }
	}
</script>

<style lang="less" scoped>
	.nav{
		display: flex;
		flex-wrap: wrap;
		height:3.7rem;
		.item{
			display:flex;
			flex-direction:column;
			align-item:center;
			width:25%;
			height:50%;
			position: relative;
			
			.item-img{
				width : 1.1rem;
				margin-top:.2rem;
				position: absolute;
				left: 50%;
				transform: translateX(-50%);
			}
			.item-desc{
				width:100%;
				position: absolute;
				left: 50%;
				transform: translateX(-50%);
				text-align: center;
				bottom: .2rem;
				font-size: .28rem;
			}
		}
	}
</style>