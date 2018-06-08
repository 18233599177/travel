<template>
	<div>
		<detailbanner :sightName="sightName" :gallaryImgs="gallaryImgs" :bannerImg="bannerImg" :categoryList="categoryList"></detailbanner>	
		<detailheader></detailheader>
		<detaillist :categoryList="categoryList"></detaillist>
		<div class="bottom"></div>	
	</div>
</template>

<script>
import axios from "axios"
import detailbanner from "./components/banner.vue"
import detailheader from "./components/header.vue"
import detaillist from "./components/list.vue"
export default{
	name:"detail",
	components:{
		detailbanner,
		detailheader,
		detaillist
	},
	data(){
		return{
			sightName:"",
			bannerImg:"",
			gallaryImgs:[],
			categoryList:[]
		}
	},
	methods:{
		getDetailInfo(){
			axios.get('/api/detail.json',{
				params:{
					id:this.$route.params.id
				}
			})
			.then(this.getDetailInfoSucc)
		},
		getDetailInfoSucc(res){
			res=res.data
			if(res.ret&&res.data){
				const data=res.data
				this.sightName=data.sightName
				this.bannerImg=data.bannerImg
				this.gallaryImgs=data.gallaryImgs
				this.categoryList=data.categoryList
			}
		}
		
	},
	mounted(){
		this.getDetailInfo()
	},
	// activated(){
	// 	this.getDetailInfo()
	// 	console.log(this.$route.params.id)
	// }
}
</script>

<style scoped>
	.bottom{
		height: 50rem
	}
</style>