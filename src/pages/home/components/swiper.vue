<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
	    <!-- slides -->
		    <swiper-slide v-for="item of swiperList" :key="item.id">
		    	<img class="swiper-img" :src="item.swiperURL" alt="去哪儿门票" style="opacity: 1;">
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>
	  	</swiper>
	</div>

</template>

<script>
export default{
	name:"homeswiper",
    props:{
        swiperList:Array
    },
	data() {
      return {
        swiperOption: {
                pagination:".swiper-pagination",
                loop:true,
                autoplay:true,
                speed:3000
            }
      }
    }
}
</script>

<style scoped>
	.wrapper >>> .swiper-pagination-bullet-active{
		background: #fff
	}
	.wrapper{
		width: 100%;
		height: 0;
		padding-bottom: 26.67%;
		overflow: hidden;
	}
	.swiper-img{
		width: 100%;
	}
</style>