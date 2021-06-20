<template>
	<div class='tabbar'>
	<el-dropdown class='tabbar-left'>
	  <span class="el-dropdown-link">
	    <img src="~assets/img/icon/ic导航.png">
	  </span>
	  <el-dropdown-menu slot="dropdown" >
	    <el-dropdown-item>首页</el-dropdown-item>
	    <el-dropdown-item>数据</el-dropdown-item>
	    <el-dropdown-item>资讯</el-dropdown-item>
	    <el-dropdown-item >视频</el-dropdown-item>
	    <el-dropdown-item >日历</el-dropdown-item>
	  </el-dropdown-menu>
	</el-dropdown>
	
	
	<div class="tabbar-right">
		<img src="~assets/img/icon/ic头像.png" />
		
	</div>
	
	
</div>
</template>

<script>
	 export default {
		name:'tabbarAn',
	    data() {
	      return {
	        isCollapse: true
	      };
	    },
	    methods: {
	     
		  }
	    }
	  
	
	
</script>

<style scoped="scoped">
	.el-menu-vertical-demo:not(.el-menu--collapse) {
	    width: 200px;
	    min-height: 400px;
	  }
	  .tabbar{
		
	  }
	  
	  .tabbar-left img{
		  width: 23px;
		  height: 19px;
	  }
	  
	  .el-dropdown-link {
	      cursor: pointer;
	      color: #409EFF;
	    }
		.tabbar-left{
		  position: absolute;
		  left: 5px;
		 /* background-color: white; */
		}
	   .tabbar-right{
		  position: absolute;
		  right: 35px;
		  cursor: pointer;
	   }
	   .tabbar-right img{
	   		 width: 23px;
			 height: 23px;
	   }
</style>
