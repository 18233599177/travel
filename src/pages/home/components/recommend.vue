<template>
	<div>
		<div class="title">
			热销推荐
		</div>
		<ul>
			<router-link tag="li" class="item" v-for="(item,index) of recommendList" :key="item.id" :to="'/detail/'+item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgURL" alt="">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</router-link>
		</ul>
	</div>
</template>

<style scoped>
	.title{
		line-height: .8rem;
		text-indent: .4rem;
		background: #ccc;
	}
	.item{
		height: 1.9rem;
		overflow: hidden;
	}
	.item-img-wrapper{
		height: 100%;
		width: 1.7rem;
		overflow: hidden;
		float: left;
	}
	.item-img{
		width: 100%;
	}
	.item-info{
		width: 72%;
		float: left;
		height: 100%;
	}
	.item-title{
		height: .6rem;
		width: 100%;
		text-indent: .6rem;
		line-height: .6rem;
		font-size: .3rem;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.item-desc{
		height: .7rem;
		width: 100%;
		text-indent: .6rem;
		line-height: .7rem;
		color: #999;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.item-button{
		left: .6rem;
		top: .1rem;
		position: relative;
		height: .4rem;
		width: 1.8rem;
		border-radius: .1rem;
		color: #eee;
		background: orange;
		line-height: .4rem;
		text-align: center
	}


</style>

<script>
export default{
	name:"homerecommend",
	props:{
		recommendList:Array
	},
	data(){
		return{
			
		}
	}
}
</script>