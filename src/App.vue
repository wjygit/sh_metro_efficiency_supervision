<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
html,body{
	width: 100%;
	height: 100%;
	min-width: 800px;
}
#app {
	width: 100%;
	height: 100%;
	float: left;
}
.el-menu{
	border-right: none;
}
</style>
