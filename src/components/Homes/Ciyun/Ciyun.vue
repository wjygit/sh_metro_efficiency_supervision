<template>
	<div id='main'></div>
</template>

<script>
export default {
  name: 'ciyun',
  data () {
    return {
      yuntu:[{"key":"考勤","doc_count":12},{"key":"eam","doc_count":10},{"key":"机房","doc_count":9},{"key":"打扫","doc_count":8},{"key":"联检","doc_count":8},{"key":"学习","doc_count":7},{"key":"整理","doc_count":4},{"key":"文件","doc_count":3},{"key":"台账","doc_count":2},{"key":"工具","doc_count":2},{"key":"文档","doc_count":2},{"key":"申请","doc_count":2},{"key":"计划","doc_count":2},{"key":"上传","doc_count":1},{"key":"各类","doc_count":1},{"key":"图纸","doc_count":1},{"key":"培训","doc_count":1},{"key":"巡检","doc_count":1},{"key":"抢修","doc_count":1},{"key":"材料","doc_count":1},{"key":"案例","doc_count":1},{"key":"班组","doc_count":1},{"key":"管理","doc_count":1},{"key":"视频","doc_count":1},{"key":"设备","doc_count":1},{"key":"车间","doc_count":1}],
      arr:[]
    }
  },
  mounted(){
  	for(var i=0; i<this.yuntu.length;i++){
	     var json = {name:this.yuntu[i].key, value:this.yuntu[i].doc_count};
	     this.arr.push(json);
	     this.arr.push(json);
	}
    this.drawLine();
  },
  methods: {
    drawLine(){
        let chart = this.$echarts.init(document.getElementById('main'))
        chart.setOption({
            tooltip: {},
            series: [{
                type: 'wordCloud',
	            gridSize: 6,
	            sizeRange: [12, 25],
	            rotationRange: [0,0],
	            shape: 'smooth',
	            width: 300,
	            height: 200,
	            textStyle: {
	                normal: {
	                    color: function () {
	                        return 'rgb(' + [
	                            Math.round(Math.random() * 250)+100,
	                            Math.round(Math.random() * 250)+100,
	                            Math.round(Math.random() * 250)+100
	                        ].join(',') + ')';
	                    }
	                },
	                emphasis: {
	                    shadowBlur: 10,
	                    shadowColor: '#333'
	                }
	            },
	            data:this.arr
            }]
        })
    }
  }
}
</script>

<style scoped>
	
	#main {
        width: 100%;
        height: 100%;
        margin: 0;
    }
	
</style>