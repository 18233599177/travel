<template>
	<div class="container" @click="handleClick">
		<div class="wrapper">
			<swiper :options="swiperOption">
			    <swiper-slide v-for="(item,index) in imgs" :key="index">
			    	<img class="gallary-img" :src="item" alt="">
			    </swiper-slide> 
			    <div class="swiper-pagination"  slot="pagination"></div>
		  	</swiper>		
		</div>
	</div>
</template>

<style scoped>
	.wrapper >>> .swiper-pagination-bullet-active{
		background: #fff
	}
	.swiper-pagination{
		color: #fff;
	}
	.container{
		display: flex;
		flex-direction: column;
		justify-content: center;
		left: 0;
		right: 0;
		top: 0;
		bottom: 0;
		background: #000;
		position: fixed;
		z-index: 99
	}
	.wrapper{
		width: 100%;
	}
	.gallary-img{
		width: 100%
	}
</style>

<script>
export default{
	name:"commongallary",
	data(){
		return{
			swiperOption:{
				pagination:".swiper-pagination",
				paginationType:"fraction",
				observeParents:true,
				observer:true
			}
		}
	},
	props:{
		imgs:{
			type:Array,
			default(){
				return []
			}
		}
	},
	methods:{
		handleClick(){
			this.$emit("close")
		}
	}
}
</script>