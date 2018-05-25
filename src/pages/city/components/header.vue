<template>
	<div class="cityheader">
		<router-link to="/">
			<div class="cityheader-back iconfont">&#xe624;</div>
		</router-link>
		<div class="cityheader-title">城市选择</div>
		<div class="cityheader-choice">
			<div class="cityheader-choice-wrapper">
				<div class="cityheader-choice-churchyard" :class="activechurch" @click="handleClickchurch">境内</div>
				<div class="cityheader-choice-overseas":class="activeover" @click="handleClickover">境外~港澳台</div>			
			</div>
		</div>
	</div>
</template>

<script>
export default{
	name:"cityheader",
	data(){
		return{
			activechurch:{active:"active"},
			activeover:{}
		}
	},
	methods:{
		handleClickchurch:function(){
			this.activechurch={active:"active"}
			this.activeover={}
		},
		handleClickover(){
			this.activechurch={}
			this.activeover={active:"active"}
		}
	}

}
</script>

<style scoped>
	.cityheader{
		width: 100%;
		height: 1.72rem;
		background: #00bcd4;
	}
	.cityheader-back{
		height: .86rem;
		color: #fff;
		width:.5rem;
		float: left;
		line-height: .86rem;
		text-align: center;
		font-size: .4rem;
		position: relative;
		left: .25rem;
	}
	.cityheader-title{
		height: .86rem;
		width: 60%;
		background: #00bcd4;
		line-height:.86rem;
		text-align: center;
		font-size: .4rem;
		color: #fff;
		margin: 0 auto;
	}
	.cityheader-choice{
		height: .86rem;
		width: 100%;
	}
	.cityheader-choice-wrapper{
		top: 10px;
		height: .5%;
		width: 70%;
		margin: 0 auto;	
	}
	.cityheader-choice-churchyard,.cityheader-choice-overseas{
		width: 50%;
		height: .5rem;
		border: 1px solid #fafafa;
		box-sizing: border-box;
		line-height: .5rem;
		text-align: center;
		float: left;
		color: #fff
	}	
	.active{
		background: #fff;
		color: #00bcd4;
	}
</style>