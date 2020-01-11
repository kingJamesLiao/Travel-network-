<template>
	<div class="calendar">
		<ul class='calendar-title calendar-box border-bottom'>
			<li @click="handleTicket">门票</li>
      		<li @click="handleTourist">一日游</li>
		</ul>
		<div class="calendar-item" v-for="(item) in calendarInfo">
			<h3 class="border-bottom" ref="gouzi">{{item.calendarInfo.title}}</h3>
			<div class="calendar-info border-bottom" v-for='result in item.calendarInfo.result'
				@click="handleClick(result)"
			>
				<div class="calendar-left">
		          <h4 class="calendar-title">{{result.subtitle}}</h4>
		        </div>
		        <div class="calendar-right">		
		        	<span>¥{{result.price}}<i class='iconfont icon-jiantouxiangxia' :style="result.styleObj"></i></span>
		        </div>
		        <detail-recommend :recommendInfo="result.recommendInfo" v-show="result.isShow"
		        ></detail-recommend>
			</div>
		</div>
	</div>
</template>

<script>
	import DetailRecommend from '@/components/detail/base/Recomment'
	export default{
		 name : 'DetailCalendar',
		 props : ['calendarInfo'],
		 data(){
		 	return{}
		 },
		 components : {
		 	DetailRecommend
		 },
		 methods : {
		 	handleClick(result){
		 		result.isShow = !result.isShow;
		 		result.styleObj.transform = 'rotate('+ result.isShow * 180 +'deg)';

		 	},
		 	handleTicket(){
		 		console.log(this.$refs.gouzi[0].offsetTop);
		 	    document.documentElement.scrollTop = this.$refs.gouzi[0].offsetTop-85
		 	},
		 	handleTourist(){
		        console.log(this.$refs.gouzi[2].offsetTop)
		        document.documentElement.scrollTop = this.$refs.gouzi[2].offsetTop-43
		      }
		 }
	}
</script>

<style lang="less" scoped>
	.border::before{
     	 border-color:#a5e4ec;
	}
	.border-bottom::before{
				border-color:#ccc;
		}
	.calendar{
		.recommend{
			 width : 100%;
			 background-color:#f5f5f5;
			 animation: fadenum 2s infinite;
			 transition: all 5s; 
		}
		.calendar-item{
			padding : 0 .2rem;
			border-bottom:.2rem solid #f5f5f5;

			h3{
				line-height : 1rem;
				font-size : .32rem;
			}
			.calendar-info{
				display:flex;
		        flex-wrap: wrap;
		        justify-content:space-between;
		        padding: .1rem 0;
		        .calendar-left{
		        	 width : 80%;
		        	 color:#616161;
		        	 h4{
		        	 	 display: -webkit-box;

				          overflow:hidden;
				          line-height:.6rem;
				          font-size:.28rem;
				          -webkit-line-clamp: 2;
				          -webkit-box-orient: vertical;
		        	 }
		        }
		        .calendar-right{
		        	display:flex;
		        	flex-direction:column;
       			    justify-content:center;
       			    width:18%;
        		    text-align:center;
        		    span{
        		    	  color:#ff9852;
				          font-size:.35rem;
				          font-weight:400;
				          padding-right:.3rem;
				          &::first-letter{
				            font-size:.24rem;
				          }
				          i{
				          	  position:absolute;
				          	  padding-left:.05rem;
					          font-size:.34rem;
					          color:#bbb;
				          }
        		    }
		        }
			}
		}
		.calendar-title{
			display:-webkit-flex;
		

			li{
				width : 50%;
				height:.8rem;
		        line-height:.8rem;
		        text-align:center;
		        font-size:.3rem;
		       	background:#f5f5f5;
		        
			}
		}
	}
</style>