<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) of pages" :key="index">
				 <div class="icon" v-for="(item,index) of page " :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgURL" :alt="item.desc" style="opacity: 1;">
					</div>
					<p class="icon-desc">
						{{item.desc}}
					</p>
				</div>
			</swiper-slide>
			<div class="swiper-pagination"  slot="pagination"></div>
		</swiper>	
	</div>
</template>

<style scoped>
	.icons>>>.swiper-pagination-bullet-active{
		background: blue
	}
	.icons>>>.swiper-container{
		height: 0;
		padding-bottom: 50%;
	}
	.icons{
		width: 100%;
		height: 0;
		padding-bottom: 50%;
		overflow: hidden;
	}	
	.icon{
		position: relative;
		overflow: hidden;
		float: left;
		width: 25%;
		padding-bottom: 25%;
	}
	.icon-img{
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		bottom: .44rem
	}
	.icon-img-content{
		height: 100%;
		display: block;
		margin:0 auto;
		box-sizing: border-box;
		padding: .1rem
	}
	.icon-desc{
		position: absolute;
		bottom: 0;
		color: #333;
		line-height: .44rem;
		height: .44rem;
		width: 100%;
		text-align: center;
	}
</style>

<script>
export default{
	name:"homeicons",
	data() {
      	return {
        	swiperOption: {
    			pagination:".swiper-pagination",
        	},
        	iconList:[
        		{
        			id:"001",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
        			desc:"景点门票"
        		},	{
        			id:"002",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png",
        			desc:"一日游"
        		},	{
        			id:"003",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png",
        			desc:"自然景光"
        		},	{
        			id:"004",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png",
        			desc:"水上乐园"
        		},	{
        			id:"005",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png",
        			desc:"亲子游"
        		},	{
        			id:"006",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png",
        			desc:"名胜古迹"
        		},	{
        			id:"007",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png",
        			desc:"海滨渔岛"
        		},	{
        			id:"008",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png",
        			desc:"本地游玩"
        		},	{
        			id:"009",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png",
        			desc:"必玩榜单"
        		},	{
        			id:"010",
        			imgURL:"http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png",
        			desc:"全部游乐"
        		},
        	],

    	}
    },
    computed:{
        pages(){
        	const pages=[]
        	this.iconList.forEach((item,index)=>{
        		const page=Math.floor(index/8)
        		if(!pages[page]){
        			pages[page]=[]
        		}
        		pages[page].push(item)
        	})
        	return pages
        }
    }
}
</script>