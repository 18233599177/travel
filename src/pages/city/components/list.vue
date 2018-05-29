<template>
	<div class="list" ref="list">
		<div ref="content">
			<div class="area">
				<div class="title" :GN="GN" :GJ="GJ">热门城市</div>
				<div class="items" v-if="GN">
					<div class="hotCity" v-for="(hotCity,index) of GNhotCitys" :key="index">
						{{hotCity.item}}
					</div>				
				</div>
				<div class="items" v-if="GJ">
					<div class="hotCity" v-for="(hotCity,index) of GJhotCitys" :key="index">
						{{hotCity.item}}
					</div>				
				</div>
			</div>
			<div class="area">
				<div class="title">字母排序</div>
				<div class="items" v-if="GN">
					<div class="a" v-for="(a,index) of GNABC" :key="index" @click="GNhandleClick" :upper="upper=a.toUpperCase()">
						{{upper}}
					</div>
				</div>
				<div class="items" v-if="GJ">
					<div class="a" v-for="(a,index) of GJABC" :key="index" @click="GJhandleClick" :upper="upper=a.toUpperCase()">
						{{upper}}
					</div>
				</div>
			</div>
			<div class="area" v-for="(items,key) of GNcitys" :key="key" :ref="items.a" v-if="GN">
				<div class="title">{{items.a}}</div>
				<div class="items">
					<div class="city" v-for="(city,index) of items.item" :key="index">
						{{city}}
					</div>
				</div>
			</div> 
			<div class="area" v-for="(items,key) of GJcitys" :key="key" :ref="items.a" v-if="GJ">
				<div class="title">{{items.a}}</div>
				<div class="items">
					<div class="city" v-for="(city,index) of items.item" :key="index">
						{{city}}
					</div>
				</div>
			</div>
			<div class="bottom"></div>
		</div>
	</div>
</template>

<script>
import BScroll from 'better-scroll'
export default{
	name:"citylist",
	props:{
		GNhotCitys:Array,
		GNABC:Array,
		GNcitys:Array,
		GJhotCitys:Array,
		GJABC:Array,
		GJcitys:Array,
		GN:Boolean,
		GJ:Boolean
	},
	data(){
		return{
			word:""
		}
	},
	mounted(){
		this.scroll=new BScroll(this.$refs.list)
	},
	methods:{
		GNhandleClick(e){
			console.log(e.target.innerText.toUpperCase())
			this.word=e.target.innerText.toUpperCase()
		},
		GJhandleClick(e){
			console.log(e.target.innerText.toUpperCase())
			this.word=e.target.innerText.toUpperCase()
		}
	},
	watch:{
		word(){
			if(this.word){
				console.log(this.word)
				const element=this.$refs[this.word][0]
				console.log(element)
				this.scroll.scrollToElement(element)
			}
		}
	}
}
</script>

<style scoped>
	.list{
		position: absolute;
		top: 2.44rem;
		left: 0;
		right: 0;		
		bottom:0rem;
		overflow: hidden;
	}
	.area{
		clear: both;
		width: 100%;
		height: auto;
	}
	.title{
		height: .72rem;
		width: 100%;
		box-sizing: border-box;
		padding-left: .2rem;
		background: #eee;
		line-height: .72rem;
	}
	.items{
		width: 100%;
		height: auto;
	}
	.hotCity{
		width: 33.3%;
		float: left;
		height: 1rem;
		line-height: 1rem;
		text-align: center;
		box-sizing: border-box;
		border: 1px solid #eee
	}
	.city{
		width: 25%;
		float: left;
		height: 1rem;
		line-height: 1rem;
		text-align: center;
		box-sizing: border-box;
		border: 1px solid #eee
	}
	.a{
		width: 16.66%;
		float: left;
		height: .96rem;
		line-height: .96rem;
		text-align: center;
		box-sizing: border-box;
	}
	.bottom{
		width: 100%;
		clear: both
	}
</style>