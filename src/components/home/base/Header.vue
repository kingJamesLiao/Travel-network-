<template>
	<div class="header">
		<i class="el-icon-arrow-left headerBack"></i>
		<div class="headerInput">
			<i class="el-icon-search  headerInputIcon"></i>
			<input type="text" placeholder="输入城市/景点/游戏主题"/>
		</div>
		<router-link tag="div" to="/city" class="headerRight">
			<span>{{$store.state.city}}</span>
			<i class="el-icon-caret-bottom"></i>
		</router-link>
	</div>
</template>
<script>
 export default {
		name : 'Header',
		data() {
			return {}
		}
	}
</script>

<style lang="less" scoped>
@homeColor : #00bcd4;
 .header{
 	display:flex;
 	height:.88rem;
 	background-color:@homeColor;
 	line-height:.88rem;
 	color:#fff;
 	.headerBack{
 		width:.88rem;
 		text-align:center;
 		line-height:.88rem;
 		font-size:.4rem;
 	}
 	.headerInput{
 		flex:1;
		border: 0px;
		height:.64rem;
		background-color:#fff;
		line-height:.64rem;
		padding-left:.1rem;
		margin-top:0.12rem;
		border-radius:.1rem;
		font-size:.3rem;

		.headerInputIcon{
			color:#ccc;
			vertical-align:middle;

		}
		input{
			border:none;
			vertical-align:middle;
			font-size:.26rem;
			color:#666;
			width:80%;
		}
		input::-webkit-input-placeholder {
		   color:#ccc;
		}
 	}
 	.headerRight {
 		width:1.2rem;
 		text-align:center;
 		font-size:.25rem;

 		span{
 			text-align:center;
 			text-indent:.5rem;
 		}
 		.el-icon-caret-bottom{
 			font-size:.3rem;

 		}
 	}
 	
 }
</style>