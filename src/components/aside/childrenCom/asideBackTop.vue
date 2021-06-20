<template>
<div>
  <el-backtop v-if='screenWidth>1381':right='15' :bottom='100' ><div class='top'><img src="~assets/img/icon/置顶.png"> </div></el-backtop>
 <!-- <el-backtop v-else :bottom='35' :right='170' ref='backtop'><div class='top'><img src="~assets/img/icon/置顶.png"> </div></el-backtop> -->
  
  <el-backtop v-if='screenWidth<1381' :right='0' :bottom='100' ><div class='top'><img src="~assets/img/icon/置顶.png"> </div></el-backtop>
  
  
  
  </div>
</template>

<script>
	export default{
		name:"asideBackTop",
		props:{
			screenWidth:{
				type:Number,
				default:0
			}
		},
		// mounted() {
		// 	if(this.screenWidth<500)
		// 	this.timer=setInterval(()=>{
		// 		this.$refs.backtop.$el.style.display='none';
		// 	},5000)
		// }
	}
</script>

<style>
	.top{
		height: 100%;
		width: 50px;
		height: 50px;
		border-radius: 50%;
		background-color: #f2f5f6;
		box-shadow: 0 0 6px rgba(0,0,0, .12);
		text-align: center;
		line-height: 40px;
		color: #1989fa;
	}
	.top img{
		width: 50px;
		height: 50px;
	}
	
	
	@media screen and (max-width: 1223px) {
			.top{
			width: 42px;
			height: 42px;
			}
			.top img{
				width: 33px;
				height: 33px;
				margin-top: 5px;
			}
			
			
		}
	
	
	
</style>
