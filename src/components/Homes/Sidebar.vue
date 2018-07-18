<template>
<div class="bgcbl">
	<div class="sidebar" :style={width:sid_width}>
		<div class="sidebar1">
		    <div class="tit"> <img src="../../../static/images/logo.png"  @click='yc_sidebar'/> <span>{{logo}}</span></div>
		    <Col span="8">
			    <Menu :theme="theme" active-name="1-2" :open-names="['']">
			        <Submenu  v-for='(x,y) in cbldata' :name='y' :key = 'y'>
			            <template slot="title">
			                <Icon type="ios-paper"></Icon>
			            		{{x.dept_name}}
			            </template>
			            <Submenu :name="y+'-1'">
				            <template slot="title">
			                	{{x.line_name==null?'暂无数据':x.line_name}}
				            </template>
				            <MenuItem :name="y+'-1-1'">{{x.team_name==null?'暂无数据':x.team_name}}</MenuItem>
		        		</Submenu>	
			        </Submenu>
			    </Menu>
		    </Col>
	    </div>
	</div>
	
	<div class="datacard">
		<div class="datacard1">
		    <div class="tit1">
		   		<div class="logoimg" :style={width:logw,marginLeft:logml}><img src="../../../static/images/logo.png" @click="xs_sidebar"/></div>
		   		<div class="ipt" :style={width:inpw,marginLeft:inpml}><input type="text" placeholder="查找人员、班组、线路、部门"/> <img src="../../../static/images/sousuo.svg" /> </div>
		    </div>
		    <div class="rwxc" :style={backgroundColor:bagca}>
		   		<div class="rwxc_name">张全蛋</div>
		   		<div class="rwxc_zyms">火雷呆·加Q来</div>
		   		<div class="rwxc_zwei">质检员</div>
		    </div>
		    
		    <div class="rycy">
		    	
		    	
		    	
		    </div>
		    <div class="ciyun">
		    	<Ciyun></Ciyun>
		    </div>
		    <div class="ygtx">
		    	
		    </div>
		    
	    </div>
	</div>
</div>
</template>

<script>
import Ciyun from './Ciyun/Ciyun'	
export default {
  name: 'Sidebar',
  data () {
    return {
      logo: '上海地铁人员效能管理',
      bagca:'rgb(' + [Math.round(Math.random() * 160)+80,Math.round(Math.random() * 160)+80,Math.round(Math.random() * 160)+80].join(',') + ')',
      cbldata:[{"dept":"TH11","dept_name":"维护一部","line":"01","line_name":"一号线","team":"TH110102","team_name":"通信2组"},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":null,"team":"TH110207","team_name":null},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":"二号线","team":"TH110210","team_name":"二东委外车载组"},{"dept":"TH11","dept_name":"维护一部","line":"01","line_name":"一号线","team":"TH110102","team_name":"通信2组"},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":null,"team":"TH110207","team_name":null},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":"二号线","team":"TH110210","team_name":"二东委外车载组"},{"dept":"TH11","dept_name":"维护一部","line":"01","line_name":"一号线","team":"TH110102","team_name":"通信2组"},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":null,"team":"TH110207","team_name":null},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":"二号线","team":"TH110210","team_name":"二东委外车载组"},{"dept":"TH11","dept_name":"维护一部","line":"01","line_name":"一号线","team":"TH110102","team_name":"通信2组"},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":null,"team":"TH110207","team_name":null},{"dept":"TH11","dept_name":"维护一部","line":"02","line_name":"二号线","team":"TH110210","team_name":"二东委外车载组"}],
      sid_width:'217px',
      theme:'dark',
      logw:'0px',
      logml:'0px',
      inpw:'300px',
      inpml:'15px',
    }
  },
  methods: {
  	yc_sidebar(){
  		this.sid_width='0px'
  		this.logml='14px'
  		this.logw='26px'
  		this.inpw='241px'
  		this.inpml='30px'
  	},
  	xs_sidebar(){
  		this.sid_width='217px'
  		this.logml='0px'
  		this.logw='0px'
  		this.inpw='300px'
  		this.inpml='15px'
  	}
  },
  mounted(){
  	
  },
  components:{
	Ciyun,
  }
}




</script>

<style scoped>
.sidebar{
	height: 100%;
	transition: all 0.5s;
	float: left;
	overflow: hidden;
	position: relative;
}
.sidebar1{
	width:320px;
	height: 100%;
	background: #001529;
	float: left;
	overflow-y:auto;
	overflow-x:hidden;
	transition: all 0.5s;
}
.tit{
	width: 217px;
	height: 54px;	
	background-color: #002140;
	position: absolute;
	top: 0;
	z-index: 999;
}
.tit img{
	width: 26px;
	height: 26px;
	margin-top: 15px;
	margin-left: 14px;
	float: left;
}
.tit img:hover{
	cursor: pointer;
}
.tit span{
	float: left;
	color: rgba(255, 255, 255, 0.7785714285714286);
	font-size: 13px;
	line-height: 54px;
	padding-left: 10px;
}
.ivu-col-span-8{
	width: 100%;
}


.datacard{
	float: left;
	width: 330px;
	height: 100%;
	overflow: hidden;
}
.datacard1{
	float: left;
	width: 350px;
	height: 100%;
	background-color: #212943;
	overflow: auto;
}
.datacard::-webkit-scrollbar {display: none;}
.tit1{
	width:330px;
	height: 54px;
	position: absolute;
	top: 0;
	z-index: 999;
}
.logoimg{
	height: 26px;
	margin-top: 15px;
	float: left;
	transition: 0.5s;
	cursor: pointer;
}
.logoimg>img{
	width: 100%;
	height: 100%;
}
.ipt{
	float: left;
	height: 26px;
	margin-top: 15px;
	position: relative;
	transition: 0.5s;
}
.ipt input{
	width: 100%;
	height: 26px;
	line-height: 26px;
	text-indent: 8px;
	color: rgba(204, 204, 204, 1);
	background-color: rgba(102, 102, 102, 0.5);
	font-size: 11px;
	text-align: left;
	border-radius: 3px;
	border: none;
	outline: none;
	box-sizing: border-box;
	padding-right: 28px;
}
.ipt img{
	width: 20px;
	height: 20px;
	position: absolute;
	right: 5px;
	top: 4px;
}

.rwxc{
	width: 330px;
	height: 226px;
	position: relative;
}
.rwxc_name{
	padding-left: 5px;
	padding-right: 27px;
	height: 48px;
	background-color:rgba(0,0,0,0.175);
	line-height: 48px;
	font-size: 28px;
	color:#fff;
	position: absolute;
	top: 124px;
	left: 15px;
}
.rwxc_zyms{
	padding-left: 5px;
	padding-right: 13px;
	height: 22px;
	line-height: 22px;
	position: absolute;
	top: 174px;
	left: 15px;
	font-size: 16px;
	color: rgba(255, 255, 255, 0.7);
	background-color: rgba(0, 0, 0, 0.375);
}

.rwxc_zwei{
	padding-left: 5px;
	padding-right: 13px;
	height: 22px;
	line-height: 22px;
	position: absolute;
	top: 198px;
	left: 15px;
	font-size: 16px;
	color: rgba(255, 255, 255, 0.7);
	background-color: rgba(0, 0, 0, 0.375);
}	

.ciyun{
	width: 330px;
	height:250px;
}

.rycy{
	width: 100%;
	height: 300px;
}
</style>
