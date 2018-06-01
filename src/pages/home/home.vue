<template>
	<div>
		<homeheader></homeheader>
		<homeswiper :swiperList="swiperList"></homeswiper>
		<homeicons :iconList="iconList"></homeicons>
		<homerecommend :recommendList="recommendList"></homerecommend>
		<homeweekend :weekendList="weekendList"></homeweekend>
	</div>
</template>

<script>
import axios from "axios"
import homeheader from './components/header.vue'
import homeswiper from './components/swiper.vue'
import homeicons from './components/icons.vue'
import homerecommend from './components/recommend.vue'
import homeweekend from './components/weekend.vue'
import {mapState} from 'vuex'
export default {
	name:"home",
	components:{
		homeheader,
		homeswiper,
		homeicons,
		homerecommend,
		homeweekend
	},
	data(){
		return{
			lastCity:"",
			swiperList:[],
			iconList:[],
			recommendList:[],
			weekendList:[]
		}
	},
	computed:{
		city: {
			get(){
      			return this.$store.state.city    
			}
      	}
	},
	methods:{
		getHomeInfo(){
			axios.get('/api/index.json?city='+this.city)
			.then(this.getHomeInfoSucc)
		},
		getHomeInfoSucc(res){
			res=res.data
			if(res.ret&&res.data){
				const data=res.data
				this.swiperList=data.swiperList
				this.iconList=data.iconList
				this.recommendList=data.recommendList
				this.weekendList=data.weekendList
			}
		}
		
	},
	mounted(){
		this.lastCity=this.city
		this.getHomeInfo()
	},
	activated(){
		if(this.lastCity!=this.city){
			this.lastCity=this.city
			this.getHomeInfo()
		}
	}
}
</script>

<style>
</style>
