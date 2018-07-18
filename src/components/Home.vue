<template>
	<div class="home">
		<Sidebar></Sidebar>
		<Chartarea></Chartarea>
	</div>
</template>

<script>	
import Sidebar from './Homes/Sidebar'
import Chartarea from './Homes/Chartarea'

export default {
  name: 'Home',
  components:{
	Sidebar,
	Chartarea
  }
}
</script>

<style scoped>
.home{
	height: 100%;
	display: flex;
}
</style>