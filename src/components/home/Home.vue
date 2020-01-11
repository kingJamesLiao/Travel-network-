<template>
	<div class="home">
		<home-header></home-header>
		<div class="contaniner" ref="wrapper">
		<div>
			<home-swiper :swiperList = "swiperList"></home-swiper>
			<home-nav :imgsList="iconList"></home-nav>
			<home-favourite :favList="recommendList"></home-favourite>
			<home-weekend :weekendList="weekendList"></home-weekend>
		</div>
		</div>
	</div>
</template>

<script>
	import {getHome} from '@/api/index.js';
	import HomeHeader from "./base/Header.vue";
	import HomeSwiper from "./base/Swiper.vue";
	import HomeNav from "./base/Nav.vue"
	import HomeFavourite from "./base/Favourite.vue"
	import HomeWeekend from "./base/Weekend.vue"
	import BScroll from 'better-scroll'
	export default {
		name  : 'Home',
		components : {
			HomeHeader,
			HomeSwiper,
			HomeNav,
			HomeFavourite,
			HomeWeekend
		},
		data(){
			return {
				iconList:[],
				recommendList : [],
				swiperList : [],
				weekendList:[]
			}
		},
		methods:{
			async getData(){
				let {iconList ,recommendList ,swiperList , weekendList} = await getHome()
				this.iconList = iconList
				this.recommendList = recommendList
				this.swiperList = swiperList
				this.weekendList = weekendList
			}
		},
		created(){
			this.getData()
		},
		mounted(){
			this.scroll = new BScroll(this.$refs.wrapper , {
				click : true
			})
		}
		// activated(){
		// 	this.getData();
		// },
		// deactivated(){
		// 	console.log('2')
		// }
	}
</script>

<style lang="less" scoped>
	.contaniner{
		position : fixed;
		overflow : hidden;
		right : 0;
		left : 0;
		bottom : 0;
		top : .88rem;
	}
</style>