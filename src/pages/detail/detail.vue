<template>
	<div>
		<detailbanner></detailbanner>	
		<detailheader></detailheader>
		<div class="bottom"></div>	
	</div>
</template>

<script>
import detailbanner from "./components/banner.vue"
import detailheader from "./components/header.vue"
export default{
	name:"detail",
	components:{
		detailbanner,
		detailheader,
	}
}
</script>

<style scoped>
	.bottom{
		height: 50rem
	}
</style>