<template>
	<div class="detail">
		<detail-banner
			:sightName="sightName"
		    :bannerImg='bannerImg'
		    :gallaryImgs="gallaryImgs"
		></detail-banner>
		<detail-header></detail-header>
		<detail-card :cardInfo="cardInfo"></detail-card>
		<h3 class="border-bottom">去哪儿推荐</h3>
		<detail-recomment :recommendInfo="recommendInfo">
		</detail-recomment>
		<detail-calendar :calendarInfo="calendarInfo"></detail-calendar>
		<detail-comment :commentInfo="commentInfo"></detail-comment>
	</div>
</template>

<script>
	
	import {getDetails} from '@/api'
	import DetailBanner from './base/Banner.vue'
	import DetailHeader from './base/Header.vue'
	import DetailCard from './base/Card.vue'
	import DetailRecomment from './base/Recomment.vue'
	import DetailCalendar from './base/Calendar'
	import DetailComment from './base/Comment'
	export default {
		name : 'Detail',
		data(){
			return{
				  sightName:'',
		          bannerImg:'',
		          gallaryImgs:[],
		          cardInfo:{},
		          recommendInfo:[],
		          calendarInfo:[],
		          commentInfo:[]
			}
		},
		components : {
			DetailBanner,
			DetailHeader,
			DetailCard,
			DetailRecomment,
			DetailCalendar,
			DetailComment
		},
		methods: {
			async getData(){
			  let {sightName,bannerImg,gallaryImgs,cardInfo,recommendInfo,calendarInfo,commentInfo} = await getDetails(this.$route.params.id)

			      this.bannerImg = bannerImg
		          this.sightName = sightName
		          this.gallaryImgs = gallaryImgs
		          this.cardInfo = cardInfo
		          this.recommendInfo = recommendInfo
		          this.calendarInfo = calendarInfo
		          this.commentInfo = commentInfo

			}
		},
		activated(){
			this.getData();
		}
	}
</script>

<style lang="less" scoped>
	h3{
		    line-height: 1rem;
    		font-size: 0.32rem;
    		padding-left:.2rem;
    		color : #666;
	}
	.border-bottom::before{
				border-color:#ccc;
		}
</style>