<template>
	<div>
		<div class="title">
			热销推荐
		</div>
		<ul>
			<li class="item" v-for="(item,index) of recommendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgURL" alt="">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
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
	data(){
		return{
			recommendList:[
				{
					id:"001",
					imgURL:"http://img1.qunarzz.com/sight/p0/201305/31/059a23e51a5cab27c8d65eac.jpg_200x200_f7ba3796.jpg",
					title:"黄金海岸",
					desc:"浪漫的海洋世界唯美的世界"
				},	{
					id:"002",
					imgURL:"http://img1.qunarzz.com/sight/p0/1707/68/6857311108984e5ea3.img.jpg_200x200_86426f1e.jpg",
					title:"渔岛",
					desc:"浪漫的海洋世界唯美的世界"
				},	{
					id:"003",
					imgURL:"http://img1.qunarzz.com/sight/p0/1612/52/52395bcad168baa3.water.jpg_200x200_da526cd0.jpg",
					title:"黄金海岸",
					desc:"浪漫的海洋世界唯美的世界"
				},	{
					id:"004",
					imgURL:"http://img1.qunarzz.com/sight/p0/201305/31/059a23e51a5cab27c8d65eac.jpg_200x200_f7ba3796.jpg",
					title:"了岛",
					desc:"浪漫的海洋世界唯美的世界"
				},	{
					id:"005",
					imgURL:"http://img1.qunarzz.com/sight/p0/1408/18/7150b0eb744ab4fc2884583e8f1b81b1.jpg_200x200_c4c4dd49.jpg",
					title:"仙螺岛",
					desc:"浪漫的海洋世界唯美的世界"
				},
			]
		}
	}
}
</script>