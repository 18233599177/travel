<template>
	<div class="search">
		<input type="text" placeholder="请输入城市名">
	</div>
</template>

<script>
export default{
	name:"citysearch"
}
</script>

<style scoped>
	.search{
		height: .72rem;
		width: 100%;
		background: #00bcd4;
	}
	.search>input{
		display: block;
		width: 70%;
		height: .6rem;
		border-radius: 5px;
		margin: 0 auto;
		box-sizing: border-box;
		padding-left: 15px;
		text-align: center
	}
	input::-webkit-input-placeholder{
        color:#ccc;
    }
</style>