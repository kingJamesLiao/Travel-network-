<template>
	<div class="city">
		<city-header></city-header>
		<city-search :cities="cities"></city-search>
		<city-list :hotCities="hotCities" :cities="cities"></city-list>
		<city-alphabet :cities="cities"></city-alphabet>
	</div>
</template>

<script>
	import {getCities} from '@/api'
	import CityHeader from './base/Header.vue';
	import CitySearch from './base/Search.vue';
	import CityAlphabet from './base/Alphabet.vue';
	import CityList from './base/List.vue';

	export default {
		name : 'City',
		components : {
			CityHeader,
			CitySearch,
			CityAlphabet,
			CityList
		},
		data(){
			return{
				hotCities : [],
				cities : []
			}
		},
		created(){
			this.getData()
		},
		methods : {
			async getData(){
				let {hotCities , cities} = await getCities();
				this.hotCities = hotCities;
				this.cities = cities;
			}
		}
	}
</script>

<style lang="less" scoped>

</style>