<template>
	<div class="datacard">
	   <div class="datacard1">
	   		<div class="nav">
	   			<div class="nav_left">
	   				<div v-for='(x,y) in nav'  @click='index=y' :class='index==y?"bgc":""'>{{x}}</div>
	   			</div>
	   			<div class="nav_right">
			        <DatePicker type="month" placeholder="选择日期" :editable="editable" placement='left-start' style="width: 124px"></DatePicker>
	   			</div>
	   		</div>
	   		<div class="rwxc_zi"></div>
	   </div>
	</div>
</template>

<script>
export default {
name: 'Datacard',
data () {
    return {
      index:1,
      editable:false,
      nav:['决策辅助','效能画像','专题分析','风险管理']
    }
}
}
</script>

<style scoped>
.datacard{
	float: left;
	flex: 1;
	height: 100%;
	background-color: #3B3B3B;
	overflow: hidden;
	float: left;
	position: relative;
}
.datacard1{
	width: 105%;
	height: 100%;
	overflow-y:auto;
	overflow-x:hidden;
	float: left;
}
.nav{
	width: 100%;
	height: 50px;
	background-color:#001529;
	position: absolute;
	top: 0;
}
.nav_left{
	width: 400px;
	height: 100%;
	display: flex;
	float: left;
}
.nav_left div{
	flex: 1;
	height: 100%;
	line-height: 50px;
	text-align: center;
	color: #cedff1;
	font-size: 16px;
	cursor: pointer;
}
.nav_right{
	width: 124px;
	height: 100%;
	float: right;
	margin-right:27px;
	margin-top: 12px;
}	
.bgc{
	background-color: #22345b;
	color: #fff !important;
}
.rwxc_zi{
	width: 100%;
	height: 800px;
}
</style>
