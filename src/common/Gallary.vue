<template>
	<div class="gallary" @click="handleClick">
		<div class="wrapper">
		  <swiper :options="swiperOption">
	        <!-- slides -->
	        <swiper-slide v-for='(item,index) in gallaryImgs' :key='index'>
	          <img class='swiper-img' :src="item" alt="">
	        </swiper-slide>
	        <!-- Optional controls -->
	        <div class="swiper-pagination" slot="pagination"></div>
	      </swiper>
		</div>
	</div>
</template>

<script>
	export default{
		name:'CommonGallary',
		props:['gallaryImgs'],
		data(){
	    return {
	      swiperOption: {
	        pagination: {
	          el: '.swiper-pagination',
	          type:'fraction'
	        },
	        observeParents:true,
	        observer:true
	      },
	    }
	  },
	  methods :{
	  	handleClick(){
	  		this.$emit('close')
	  	}
	  }
	}
</script>

<style lang="less" scoped>
	
	.swiper-container{
		overflow:inherit;
	}
	.gallary{
		position:fixed;
	    z-index:10;
	    left:0;
	    right:0;
	    top:0;
	    bottom:0; 
	    background:#000;
	    .wrapper{
	    	position:absolute;
	    	top : 50%;
	    	bottom : 0;
	    	transform:translateY(-50%);
	    	width : 100%;
	    	height :0;
	    	padding-bottom:62.5%;
	    	background-color : #fff;
	    	

	    	.swiper-img{
	    		width :100%;

	    	}
	    	.swiper-pagination{
	    		bottom:-1rem;
      			color:#fff;
	    	}
	    }
	}
</style>