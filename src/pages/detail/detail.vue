<template>
	<div>
		<detailbanner></detailbanner>	
		<detailheader></detailheader>
		<detaillist :list="list"></detaillist>
		<div class="bottom"></div>	
	</div>
</template>

<script>
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
			list:[
				{
					title:"成人票",
					children:[
						{title:"成人三馆联票"},
						{title:"成人五馆联票"}
					]
				},{
					title:"学生票",
					children:[
						{title:"学生三馆联票"},
						{title:"学生五馆联票"}
					]
				},{
					title:"儿童票",
					children:[
						{title:"儿童三馆联票"},
						{title:"儿童五馆联票"}
					]
				}
				
			]
		}
	}
}
</script>

<style scoped>
	.bottom{
		height: 50rem
	}
</style>