<template>
	<div>
		<cityheader @GN='citylistGN' @GJ='citylistGJ'></cityheader>
		<citysearch></citysearch>
		<citylist :GNhotCitys="GNhotCitys" :GNABC="GNABC" :GNcitys="GNcitys" :GJhotCitys="GJhotCitys" :GJABC="GJABC" :GJcitys="GJcitys" :GN="GN" :GJ="GJ"></citylist>
	</div>		
</template>

<script>
import axios from "axios"
import cityheader from "./components/header.vue"
import citysearch from "./components/search.vue"
import citylist from "./components/list.vue"
export default{
	name:"city",
	components:{
		cityheader,
		citysearch,
		citylist
	},
	data(){
		return{
			GNhotCitys:[],
			GNABC:[],
			GNcitys:[],
			GJhotCitys:[],
			GJABC:[],
			GJcitys:[],
			GJ:false,
			GN:true
		}
	},
	methods:{
		getCityInfo(){
			axios.get('/api/city.json')
			.then(this.getCityInfoSucc)
		},
		getCityInfoSucc(res){
			res=res.data
			console.log(res.GNhotCitys)	
			if(res.ret){
				this.GNABC=res.GNABC
				this.GNcitys=res.GNcitys
				this.GNhotCitys=res.GNhotCitys
				this.GJABC=res.GJABC
				this.GJcitys=res.GJcitys
				this.GJhotCitys=res.GJhotCitys
			}
		},
		citylistGN(GN,GJ){
			this.GN=GN
			this.GJ=GJ
		},
		citylistGJ(GN,GJ){
			this.GN=GN
			this.GJ=GJ
		}	
	},
	mounted(){
		this.getCityInfo()
	}
}
</script>

<style scoped>
	
</style>