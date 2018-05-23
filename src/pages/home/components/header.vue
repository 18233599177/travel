<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
		</div>
		<div class="header-right">
			{{city}}<span class="iconfont">&#xe62d;</span>
		</div>
	</div>
</template>

<script>
export default {
	name:"homeheader",
	props:{
		city:String
	}
}
</script>

<style scoped>
	.header{
		height: .86rem;
		display: flex;
		background: #00bcd4;
		color: #fff;
		line-height: .86rem;
	}
	.header-input{
		flex: 1;
		border-radius: .1rem;
		background: #fff;
		height: .64rem;
		margin-top:.12rem;
		color: #ccc;
		padding-left: .1rem;
		line-height: .64rem;
	}
	.header-left{
		width: .64rem;
		float: left;
	}
	.header-right{
		width: 1.24rem;
		float: right;
		text-align: center;
	}
	.back-icon{
		text-align: center;
		font-size: .4rem;
	}
</style>
