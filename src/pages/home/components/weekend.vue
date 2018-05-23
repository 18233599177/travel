<template>
	<div>
		<div class="title">
			周末去哪玩儿
		</div>
		<ul>
			<li class="item" v-for="(item,index) of weekendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgURL" alt="">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<style scoped>
	.title{
		line-height: .8rem;
		text-indent: .4rem;
		background: #eee;
	}
	.item{
		height: 4.4rem;
		overflow: hidden;
	}
	.item-img-wrapper{
		height: 0;
		padding-bottom: 37.8%;
		width: 100%;
		overflow: hidden;
	}
	.item-img{
		width: 100%;
	}
	.item-info{
		width: 100%;
		background: #fafafa
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
	name:"homeweekend",
	props:{
		weekendList:Array
	},
	data(){
		return{
		
		}
	}
}
</script>