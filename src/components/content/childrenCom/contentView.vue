<template>
	<div class="view-content">
	
	<div class='view-title'>
		<!-- <div class="view-img"><img src="~assets/img/icon/ic折线图.png"> </div>
		<div class="view-img"><img src="~assets/img/icon/ic折线图.png"> </div> -->
		<el-tag color='white'   class="broken-line" size="medium" @click='brokenTag' ref='brokenline' ><img src="~assets/img/icon/ic折线图.png">     折线图</el-tag>
		<el-tag  color='#59aaff' class='straight-line'size="medium" @click='straightTag' ref='straight' ><img src="~assets/img/icon/ic柱状图.png">     柱状图</el-tag>
		
		
		
		<span class="view-from">数据来源：Jin10.com</span>
	</div>
	
	<!-- <div id="content-view" /> -->

		<straightline-view  v-if="isShow" ref='straightlineView'/>                     <!-- 柱状图 -->
		<brokenline-view v-else ref='brokenlineView'/>                                    <!-- 折线图 -->
		
		
		
		
		
		
	</div>
</template>

<script>
	import * as echarts from 'echarts'
	import straightlineView from './straightlineView.vue'              //柱状图组件
	import brokenlineView from './brokenlineView.vue'             //折线图组件
	export default{
		name:'contentView',
		components:{
			straightlineView,
			brokenlineView
		},
		methods:{
			brokenTag(){             
				
		
		     if(this.isShow)
			 {
			this.isShow=!this.isShow
		     }
		
		this.$refs.brokenline.$el.style.backgroundColor='#409eff';
		this.$refs.brokenline.$el.style.color='#ffffff';
		
		this.$refs.straight.$el.style.backgroundColor='#ffffff';
		this.$refs.straight.$el.style.color='#59aaff';
		
		
			
		
			},
			straightTag(){
				this.$refs.brokenline.$el.style.backgroundColor='#ffffff';
				this.$refs.brokenline.$el.style.color='#59aaff';
				
				this.$refs.straight.$el.style.backgroundColor='#409eff';
				this.$refs.straight.$el.style.color='#ffffff';
				if(!this.isShow){
					this.isShow=!this.isShow
				}	
			}
		},
		data(){
			return{
				isShow:true
			}
		},
		mounted() {
			// var myChart = echarts.init(document.getElementById('content-view'));
			// var option = {
			//             title: {
			//                 text: ''
			//             },
			//             tooltip: {},
			//             legend: {
			//                 data:['']
			//             },
			//             xAxis: {
								  
			//                 data: ["2020/4","2020/6","2020/8","2020/10","2020/12"]
			//             },
			//             yAxis: {},
			//             series: [{
			//                 name: '增长率',
			//                 type: 'bar',
			//                 data: [0.6,0.8,0.5,-0.1,  0.4, 0.3]
			//             }]
			//         };
			
			
			// // var option = {
			// //         title: {
			// //             text: ''
			// //          },
			// //         tooltip: {
			// //             trigger: 'axis'
			// //          },
			// //          legend: {
			// //              data:[]
			// //          },
			// //          grid: {
			// //              left: '3%',
			// //              right: '4%',
			// //              bottom: '3%',
			// //              containLabel: true
			// //          },
			// //          toolbox: {
			// //              feature: {
			// //                  saveAsImage: {}
			// //              }
			// //          },
			// //          xAxis: {
			// //              type: 'category',
			// //              boundaryGap: false,
			// //              data: ["2020/4","2020/6","2020/8","2020/10","2020/12"]
			// //          },
			// //          yAxis: {
			// //              type: 'value'
		 // //         },
			// //          series: [
			// //              {
			// //                  name:'增长率',
			// //                  type:'line',
			            
			// //                  data: [0.6,0.8,0.5,-0.1,  0.4, 0.3]
			// //              }
			             
			// //          ]
			// //      };
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			//           myChart.setOption(option);
		}
		
	}
</script>

<style scoped="scoped">
	/* #content-view{
		width: 600px;
		height:400px;
	} */
	
	/* .view-img{
		width: 100px;
		border: #888888 solid 2px;
		margin-top: 16px;
		margin-left: 133px;
		border-radius:5%;
		color: #898989;
		padding-top: 3px;
		padding-bottom: 3px;
		text-align: center;
		display: inline-block;
	} */
	
	
	.view-title{
		margin-top: 30px;
		position: relative;
	}
	.broken-line{
		cursor: pointer;
		margin-right: 20px;
		
		
		
	}
	.broken-line img{
		width: 25px;
		height: 19px;
		margin-top: 2px;
		margin-bottom: -3px;
		padding-right: 2px;
	}
	.straight-line{
		cursor: pointer;
		margin-right: 53%;
		color: #FFFFFF;
	}
	
	.straight-line img{
		width: 25px;
		height: 19px;
		margin-top: 2px;
		margin-bottom: -3px;
		padding-right: 2px;
	}
	.view-from{
		color: #8c8c8c;
		font-size: 13px;
		position: absolute;
		right: 10px;
	}
	
</style>
