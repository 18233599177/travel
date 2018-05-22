<template>
	<div>
		<homeheader></homeheader>
		<homeswiper></homeswiper>
		<homeicons></homeicons>
		<homerecommend></homerecommend>
		<homeweekend></homeweekend>
	</div>
</template>

<script>
import homeheader from './components/header.vue'
import homeswiper from './components/swiper.vue'
import homeicons from './components/icons.vue'
import homerecommend from './components/recommend.vue'
import homeweekend from './components/weekend.vue'
export default {
	name:"home",
	components:{
		homeheader,
		homeswiper,
		homeicons,
		homerecommend,
		homeweekend
	}
}
</script>

<style>
</style>
