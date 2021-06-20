<template>
	<div class="content-1view" >
		</div>
</template>

<script>
	import * as echarts from 'echarts'
	export default{
		name:'straightlineView',
		data(){
			return{
				myChart:null
			}
		},
		mounted() {
			this. myChart = echarts.init(document.getElementsByClassName('content-1view')[0]);
			var option = {
						        title: {
						            text: ''
						         },
						        tooltip: {
						            trigger: 'axis'
						         },
						         legend: {
						             data:[]
						         },
						         grid: {
						             left: '3%',
						             right: '4%',
						             bottom: '3%',
						             containLabel: true
						         },
						         toolbox: {
						             feature: {
						                 saveAsImage: {}
						             }
						         },
						         xAxis: {
						             type: 'category',
						             boundaryGap: false,
						             data: ["2020/4","2020/6","2020/8","2020/10","2020/12"]
						         },
						         yAxis: {
						             type: 'value'
			        },
						         series: [
						             {
						                 name:'增长率',
						                 type:'line',
						            
						                 data: [0.6,0.8,0.5,-0.1,  0.4, 0.3]
						             }
						             
						         ]
						     };
					
					this.myChart.setOption(option);
					}
					
	}
</script>

<style scoped="scoped">
	.content-1view{
		width: 81%;/* 600px; */
		height:400px;
		margin-top: 0%;
		margin-left: 10%;
		margin-bottom: 33px;
	}
</style>
