<template>
	<div>
		<homeheader></homeheader>
		<homeswiper></homeswiper>
	</div>
</template>

<script>
import homeheader from './components/header.vue'
import homeswiper from './components/swiper.vue'
export default {
	name:"home",
	components:{
		homeheader,
		homeswiper
	}
}
</script>

<style>
</style>
