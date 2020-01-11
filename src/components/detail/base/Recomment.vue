<template>
	<div class="recommend">
		<solt></solt>
		<div class="recommend-info border-bottom" v-for='item of recommendInfo'>
			<div class="recommend-left">
				<h4 class="recommend-title">{{item.title}}</h4>
				<p>{{item.time}} <span>随时退</span></p>
				
			</div>
			<div class="recommend-right">
				<span> ¥{{item.price}}</span>
				<div class='recommend-button'> {{item.type}}</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name : 'DetailComment',
		props:['recommendInfo']
	}
</script>

<style lang="less" scoped>
	.border::before{
     	 border-color:#a5e4ec;
	}
	.border-bottom::before{
				border-color:#ccc;
		}
	.recommend{
		padding:0 .2rem;
    	border-bottom:.2rem solid #f5f5f5;
    	.recommend-info{
    		display:flex;
		    justify-content:space-between;
		    .recommend-left{
				 width:80%;
			     color:#616161;
			     h4{
			     	  display: -webkit-box;
				      overflow:hidden;
				      line-height:.6rem;
				      font-size:.3rem;
				      -webkit-line-clamp: 2;
				      -webkit-box-orient: vertical;
			     }
			     p{
			     	  line-height:.8rem;
       				  font-size:.28rem;
       				  color : #ff8300;

       				  span{
				     	 color:#00afc7;
	        			 font-size:.24rem;
	        			 margin-left:.3rem;
	        			 border : 0.5px #a5e4ec solid;
			    	 }
			     }
		    }
		    .recommend-right{
		    	  display:flex;
			      flex-direction:column;
			      justify-content:center;
			      width:1.8rem;
			      text-align:center;
			      span{
			      		color:#ff9852;
				        font-size:.35rem;
				        font-weight:400;
			      }
			       .recommend-button{
			       		height:.6rem;
				        color:#fff;
				        background-image: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%);
				        line-height:.6rem;
				        border-radius:.1rem;
			       }
		    }	   
    	}
	}
	
</style>