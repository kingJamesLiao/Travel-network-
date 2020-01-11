<template>
	<div class="weekend">
		<h3 class="title">周末去哪儿</h3>
		<ul>
			<router-link
				:to="{name:'weeklink' , params : {id : item.id}}"
				v-for="(item , index) in weekendList"
				class="item border-bottom"
			    :key="index"
			>
				<img :src="item.imgUrl" alt="" class="item-img">
				<div class="item-info">
					<h4>{{item.title}}</h4>
					<p class="item-price">{{item.desc}}</p>
				</div>
			</router-link>
		</ul>
	</div>
</template>

<script>
	export default{
		name : 'HomeWeekend',
		props : ['weekendList']
	}
</script>

<style lang="less" scoped>
	.title{
		margin-top: .2rem;
	    line-height: .8rem;
	    background: #ddd;
	    text-indent: .2rem;
	    font-size: .32rem;
	}
	.item{
		.item-img{
			width : 100%;
		}
		.item-info{
			flex:1;
			padding : .1rem;
			margin-left : .1rem;
			min-width: 0rem;

			h4{
				line-height:.6rem;
      		    font-size:.3rem;
      		    color:#ffb436;
      		    font-weight : 600;
			}
			.item-price{
				font-size : .24rem;
				line-height: .4rem;
				color:#666;
			}
		}
	}
</style>