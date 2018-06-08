<template>
	<div>
		<div v-for="(item,index) of categoryList" :key="index">
			<div class="item-title">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>		
			<div v-if="item.children" class="item-children">
				<detaillist :categoryList="item.children"></detaillist>
			</div>	
		</div>
		
	</div>
	
</template>

<style scoped>
	.item-title{
		position: relative;
		width: 100%;
		height: .8rem;
		line-height: .8rem;
		border-bottom: 1px solid #eee;
		text-indent: 1rem
	}
	.item-title-icon{
		display: inline-block;
	    position: absolute;
	    width: .36rem;
	    height: .36rem;
	    top: .26rem;
	    left: .2rem;
	    background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
	    margin-right: .1rem;
	    background-size: .4rem 3rem;
	}
	.item-children{
		padding: 0 .3rem;
	}
</style>

<script>
export default{
	name:"detaillist",
	props:{
		categoryList:Array
	},
	data(){
		return{
			
		}
	}
}
</script>