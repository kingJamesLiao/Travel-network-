<template>
	<div class="alphabet">
		<ul>
			<li v-for="(item , key) in cities"
				@click="handleClick(key)"
			>{{key}}</li>
		</ul>
	</div>
</template>

<script>
	export default{
		name : 'CityAlphabet',
		props : ['cities'],
		methods : {
			handleClick(letter){
				this.$store.commit('changeLetter' , letter)
				
			}
		}
	}
</script>

<style lang="less" scoped>
	.alphabet{
		position : fixed;
		right : 0;
		top :1.6rem;
		bottom : 0;
		display : flex;
		flex-direction:column; //项目将垂直显示
		justify-content:center;	//项目将垂直居中
		width : .4rem;

		li{
			line-height: .5rem;
			text-align : center;
			color : #666;
			font-weight: 700;
			font-size:.2rem;
		}
	}
</style>