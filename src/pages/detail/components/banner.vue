<template>
	<div>
		<div class="banner" @click="showGallary=true">
			<router-link to="/">
				<div class="iconfont banner-back">&#xe624;</div>
			</router-link>	
			<img src="http://img1.qunarzz.com/sight/p0/1408/18/7150b0eb744ab4fc2884583e8f1b81b1.jpg_600x330_fabdec28.jpg" alt="" class="banner-img">
			<div class="banner-info">
				<div class="banner-title"><p>新澳海底世界（AAAA级景区）</p></div>
				<div class="banner-icon"><span class="iconfont">&#xe650;</span>39</div>
			</div>
		</div>
		<commongallary :imgs="imgs" v-show="showGallary" @close="handleClickclose"></commongallary>	
	</div>
	
</template>

<style scoped>
	.banner{
		height: 0;
		padding-bottom: 55%;
		width: 100%;
		position: relative;
	}
	.banner-back{
		box-sizing: border-box;
		position: absolute;
		top: 0.2rem;
		left: 0.2rem;
		width: .7rem;
		height: .7rem;
		background: rgba(0,0,0,.6);
		font-size: .4rem;
		color: #fff;
		line-height: .7rem;
		text-align: center;
		border-radius: 50%;
	}
	.banner-img{
		width: 100%
	}
	.banner-info{
		bottom: 0;
		width: 100%;
		position: absolute;
		height: .8rem;
		line-height: .8rem;
		font-size: .35rem;
		color: #fff;
		display: flex;
		background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
	}
	.banner-title{
		flex: 1;
		height: .8rem;
		padding-left: .3rem;
	}
	.banner-icon{
		width: 1rem;
	}
</style>

<script>
import commongallary from "@/common/gallary/gallary"
export default{
	name:"detailbanner",
	components:{
		commongallary
	},
	data(){
		return{
			showGallary:false,
			imgs:[
				"http://img1.qunarzz.com/sight/p0/1507/58/b8ef0393e1a76a0cf934bc5528fab8d6.water.jpg_r_800x800_37ea2e0f.jpg",
				"http://img1.qunarzz.com/sight/p0/1507/8e/e2b4128e4cd11a75ee7e849dcff2854a.water.jpg_r_800x800_62361814.jpg"
			]
		}
	},
	methods:{
		handleClickclose(){
			this.showGallary=false
		}
	}
}
</script>