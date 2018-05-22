<template>
	<div>
		<homeheader></homeheader>
		<homeswiper></homeswiper>
		<homeicons></homeicons>
	</div>
</template>

<script>
import homeheader from './components/header.vue'
import homeswiper from './components/swiper.vue'
import homeicons from './components/icons.vue'
export default {
	name:"home",
	components:{
		homeheader,
		homeswiper,
		homeicons
	}
}
</script>

<style>
</style>
