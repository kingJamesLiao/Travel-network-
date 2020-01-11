<template>
	<div class="header">
		<router-link tag='i' to="/" class="el-icon-arrow-left header-back"></router-link>
   	    <h2>长沙必打卡</h2>
	</div>
</template>

<script>
	export default{
		name : 'WeekHeader'
	}
</script>

<style lang="less" scoped>
	.header{
		position:relative;
	    background:#00bcd4;
	    line-height:.88rem;
	    color:#fff;
	    text-align:center;
	    
	    .header-back{
	    	  position:absolute;
		      left:0;
		      top:0;
		      color:#fff;
		      width:.88rem;
		 	  text-align:center;
		 	  line-height:.88rem;
		 	  font-size:.4rem;
	    }
	    h2{
			  text-align:center;
     		  font-size:.32rem;
	    }
	}
</style>