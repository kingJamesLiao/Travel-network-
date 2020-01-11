<template>
	<div class="week">
		<week-header></week-header>
		<week-list :weekInfo="weekInfo"></week-list>
	</div>
</template>

<script>
	import {getWeeks} from '@/api/index.js';
	import WeekHeader from './base/Header.vue'
	import WeekList from './base/List.vue'
	export default{
		name : 'Week',
		components : {
			WeekHeader,
			WeekList
		},
		data(){
			return{
				weekInfo : []
			}
		},
		activated(){
			this.getData();
		},
		methods : {
			async getData(){
				let {weekInfo} = await getWeeks(this.$route.params.id)
       		    this.weekInfo = weekInfo
			}
		}
	}
</script>

<style lang="less" scoped>

</style>