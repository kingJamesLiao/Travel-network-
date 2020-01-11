<template>
	<div class="favourite">
		<h3 class="title">猜你喜欢</h3>
		<ul>
			<router-link 
			class="item border-bottom"
			v-for="(item , index) in favList"
			:key="index"
			tag="li"
			:to="{name : 'detaillink' , params : { id : item.id}}"
			>
				<img :src="item.imgUrl" class="item-img" alt="">
				<div 
				class="item-info">
					<h4>{{item.title}}</h4>
					<div class='item-fav-info clearfix'>
						<p class='item-fav-text'>
							<i v-for="i in 5" class="iconfont icon-star"></i>
							<span class='item-fav-star'
							 :style="item.score|star"
							>
								<i v-for='i in 5' class='iconfont icon-star'></i>
							</span>
						</p>
						<p class='item-text-right'>
							<span>{{item.comment}}条评论 </span>
						</p>
					</div>
					<p class='item-price'><i>$</i><span>{{item.price}}</span></p>
				</div>
			</router-link>
		</ul>
	</div>
</template>

<script>
	export default{
		name : 'Favourite',
		props : ['favList'],
		filters : {
			star(score){
				return {
					width : score*100 / 5 + '%'
				}
			}
		}
	}	
</script>

<style lang="less" scoped>

	.title{
		margin-top:.2rem;
		line-height : .8rem;
		background-color: #ddd;
		text-indent : .2rem;
		font-size:.32rem;
	}

	.border-bottom::before{
				border-color:#777;
			}
	.item{
				display: flex;
				height: 2.2rem;
				
				padding: .2rem;
				
				
				.item-img{
					width : 2rem;
					height : 2rem;
				
					margin-top:.07rem;


					
				}

				.item-info{
					flex: 1;
					padding : .1rem;
					margin-left : .1rem;
					min-width : 0rem;
					
					h4{
						line-height : .6rem;
						font-size:.3rem;
						
					}
					.item-price{			
						color: #ff8300;
						font-size:.3rem;
						line-height:.4rem;
						
						
						span{
							font-size:.4rem;
							font-weight: bold;
						}
					}
					.item-fav-info{
						line-height : .6rem;
						
						.item-fav-text{
							position : relative;
							display:inline-block;
							float: left;
							color　: #ccc;
							margin-right:.5rem;
							
							.item-fav-star{
								overflow: hidden;
								position: absolute;
								left :0;
								top : 0;
								color　: #ffb436;
							}
						}
						.item-text-right{
							float :right;
							color:#999;
							
						}		
					}	
			}
	}
	
</style>