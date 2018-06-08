<template>
	<transition>
		<slot>
			
		</slot>	
	</transition>	
</template>

<style scoped>
	.v-enter{
		opacity: 0;
	}
	.v-leave{
		opacity: 1
	}
	.v-leave-active,.v-enter-active{
		transition:opacity .5s
	}
	.v-leave-to{
		opacity: 0
	}
</style>

<script>
export default{
	name:"commonfade",
}
</script>