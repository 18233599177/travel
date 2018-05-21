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
	data() {
      return {
        swiperOption: {
    		pagination:".swiper-pagination",
    		loop:true
        },
        swiperList:[
        	{
        		id:"0001",
        		swiperURL:"https://imgs.qunarzz.com/piao/fusion/1708/f1/ee65a13642c95c02.jpg_750x200_3440fec0.jpg"
        	},	{
        		id:"0002",
        		swiperURL:"https://imgs.qunarzz.com/piao/fusion/1804/dd/269c3dafd51a2502.jpg_750x200_4fb86e3e.jpg"
        	},  {
        		id:"0003",
        		swiperURL:"https://imgs.qunarzz.com/piao/fusion/1804/c4/1cdd28811593b802.jpg_750x200_5fbb7c91.jpg"
        	},  {
        		id:"0004",
        		swiperURL:"https://imgs.qunarzz.com/piao/fusion/1804/5e/fe34170c403d1202.jpg_750x200_40d539e1.jpg"
        	}
        ]
      }
    },
    computed: {
      swiper() {
        
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
		padding-bottom: 31.25%;
		overflow: hidden;
	}
	.swiper-img{
		width: 100%;
	}
</style>