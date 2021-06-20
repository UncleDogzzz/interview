<template>
  <div id="app">

   <!-- PC -->
<el-container v-if='screenWidth>500'>
  <el-header> <tabbar-pc  :screenWidth='screenWidth'/>   <!-- 以500为临界，PC与移动端的切换临界 -->

  </el-header>
  <el-container>
	  <el-main>
		  <textcontent  :screenWidth='screenWidth' ref='textContent'> 
		  <aside-top-recommend v-if='screenWidth<1124' />      <!-- 973为临界，宽度小于973将aside栏插入到textcontent的下面 -->
		 <!-- <aside-top-recommend v-if='screenWidth<652'  /> -->
		   </textcontent>
	  </el-main>
    <el-aside width='318px' v-if='screenWidth>1124'>           <!-- 1242为临界，宽度大于1242正常显示-->
		<aside-content :scrollTop='scrollTop' />
	</el-aside>
  </el-container>
</el-container>
   
   
   <!-- app -->
  <el-container v-if='screenWidth<500'>
    <el-header height='47px'><tabbar-an /></el-header>
    <el-main style='background-color: white;'>
	<textcontent  :screenWidth='screenWidth'> <aside-top-recommend /></textcontent>
	</el-main>
  </el-container> 
  
  
    <aside-back-top :screenWidth='screenWidth' />          <!-- //置顶组件 -->
   
   
  </div>
</template>

<script>
import tabbarPc from 'components/tabbar/tabbarPc.vue'   //PC 导航栏
import tabbarAn from 'components/tabbar/tabbarAn.vue'   //移动端 导航栏
import textcontent from 'components/content/textcontent.vue'  //内容烂
import asideContent from 'components/aside/asideContent.vue' //侧边栏
import asideTopRecommend from'components/aside/childrenCom/asideTopRecommend.vue'  //推荐栏部分
import asideBackTop from 'components/aside/childrenCom/asideBackTop.vue'          //返回顶部


export default {
  name: 'App',
  data(){
	  return {
		  screenWidth:document.documentElement.clientWidth,  //窗口宽度
		  screenHeight:document.documentElement.clientHeight, //窗口高度 
		  scrollTop:0                            //滚动距离
	  }
  },
  components: {
   tabbarPc,
   tabbarAn,
   textcontent,
   asideContent,
   asideTopRecommend,
   asideBackTop
  },
  mounted() {
      var _this = this;
      window.onresize = function(){ // 定义窗口大小变更通知事件
      _this.screenWidth = document.documentElement.clientWidth; //窗口宽度
      _this.screenHeight = document.documentElement.clientHeight; //窗口高度 
	  
	  if(_this.$refs.textContent&&_this.$refs.textContent.$refs.contentView.$refs.straightlineView){             //刷新柱状图宽度
	  _this.$refs.textContent.$refs.contentView.$refs.straightlineView.myChart.resize();
	  }
	  if(_this.$refs.textContent&&_this.$refs.textContent.$refs.contentView.$refs.brokenlineView){      //刷新折线图宽度
	  _this.$refs.textContent.$refs.contentView.$refs.brokenlineView.myChart.resize();
	 
	  }
	  
	 
	  
	  
	  
  	  };
	 
	  window.onscroll = function() {
	    //为了保证兼容性，这里取两个值，哪个有值取哪一个
	    //scrollTop就是触发滚轮事件时滚轮的高度
	    var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
	    _this.scrollTop=scrollTop;
	  };
  }
  
}
</script>

<style>
	@import '~assets/css/base.css'

</style>
