<template>
	<div>
		<div class="search">
			<input type="text" placeholder="请输入城市名" v-model="keywords">
		</div>
		<div class="search-content" ref="searchContent" v-show="show">
			<ul>
				<li v-for="(value,index) of list" :key="index" @click="handleClick(value)">{{value}}</li>
				<div class="bottom"></div>	
			</ul>			
		</div>		
	</div>
</template>

<script>
import BScroll from 'better-scroll'
export default{
	name:"citysearch",
	data(){
		return{
			keywords:"",
			list:[],
			show:false
		}
	},
	props:{
		GNcitys:Array,
		GJcitys:Array
	},
	methods:{
		handleClick(city){
			this.$store.commit("changeCity",city)
			this.$router.push("/")
		}
	},
	watch:{
		keywords(){
			if(this.keywords.trim().length>0){
				this.show=true
			}else{
				this.show=false
			}
			clearTimeout(this.time)
			this.time=setTimeout(()=>{
				const result=[]
				for(let i in this.GNcitys){
					this.GNcitys[i].item.forEach((val)=>{
						if(val.indexOf(this.keywords.trim())>-1&&this.keywords.trim()!=""){
							result.push(val)
						}
					})
				}
				// for(let i in this.GNcitys){
				// 	this.GNcitys[i].spell.forEach((val)=>{
				// 		if(val.indexOf(this.keywords.trim())>-1&&this.keywords.trim()!=""){
				// 			result.push(val)
				// 		}
				// 	})
				// }
				for(let i in this.GJcitys){
					this.GJcitys[i].item.forEach((val)=>{
						if(val.indexOf(this.keywords.trim())>-1&&this.keywords.trim()!=""){
							result.push(val)
						}
					})
				}
				// for(let i in this.GJcitys){
				// 	this.GJcitys[i].spell.forEach((val)=>{
				// 		if(val.indexOf(this.keywords.trim())>-1&&this.keywords.trim()!=""){
				// 			result.push(val)
				// 		}
				// 	})
				// }
				this.list=result		
			},100)
			
		}
	},
	mounted(){
		this.scroll=new BScroll(this.$refs.searchContent)
	}
}
</script>

<style scoped>
	.bottom{
		clear: both;
		width: 100%;
		height: 1px;
	}
	.search{
		height: .72rem;
		width: 100%;
		background: #00bcd4;
	}
	.search>input{
		display: block;
		width: 90%;
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
    .search-content{
    	z-index: 10;
    	position: absolute;
    	overflow: hidden;
    	top: 2.44rem;
    	left: 0;
    	right: 0;
    	bottom: 1px;
    	background: #fff;
    }
    .search-content>ul>li{
    	width: 33.3%;
		float: left;
		height: .96rem;
		line-height: .96rem;
		text-align: center;
		box-sizing: border-box;
		border: 1px solid #ccc;
    }
</style>