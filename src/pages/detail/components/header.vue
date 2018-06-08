<template>
	<div class="header" :style="opacityStyle" :show="show">
		<router-link tag="div" to="/"class="header-back iconfont" >&#xe624;</router-link>
	</div>
	
</template>

<style scoped>
	.header{
		width: 100%;
		height: .86rem;
		background: #00bcd4;
		position: fixed;
		left: 0;
		top: 0;
		right: 0;
	}
	.header-back{
		height: .86rem;
		color: #fff;
		width:.5rem;
		float: left;
		line-height: .86rem;
		text-align: center;
		font-size: .5rem;
		position: relative;
		left: .25rem;
		font-weight: bold;
	}
</style>

<script>
export default{
	name:"detailheader",
	data(){
		return{
			show:false,
			opacityStyle:{
				opacity:0
			}
		}
	},
	methods:{
		headerScroll(){
			console.log(1)
			if(document.documentElement.scrollTop>60){
				this.show=true
				let opacity=document.documentElement.scrollTop/200
				document.documentElement.scrollTop>200?opacity=1:opacity
				this.opacityStyle={
					opacity
				}
			}else{
				this.opacityStyle={
					opacity:0,
					show:false
				}
			}
		}
	},
	activated(){	
		console.log(1)
		window.addEventListener("scroll",this.headerScroll)
	},// 全局事件需要被解绑
	deactivated(){
		window.removeEventListener("scroll",this.headerScroll)
	}
}
</script>