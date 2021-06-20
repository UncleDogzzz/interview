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
			            tooltip: {},
			            legend: {
			                data:['']
			            },
			            xAxis: {
								  
			                data: ["2020/4","2020/6","2020/8","2020/10","2020/12"]
			            },
			            yAxis: {},
			            series: [{
			                name: '增长率',
			                type: 'bar',
			                data: [0.6,0.8,0.5,-0.1,  0.4, 0.3]
			            }]
			        };
					
					this. myChart.setOption(option);
					
					// window.onresize = function () {
						    	
					// 			console.log(123)
					// 	    }
					
					
				
			
					
					
					
					
					// window.onresize=function(){  
					//  myChart.resize();
					// } 
					
					
					
					
					
					
					
					
					
					
					
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
