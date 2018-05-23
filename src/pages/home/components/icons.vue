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
    props:{
        iconList:Array
    },
	data() {
      	return {
        	swiperOption: {
    			pagination:".swiper-pagination",
                iconList:this.iconList
        	}
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