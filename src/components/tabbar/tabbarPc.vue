<template>
	<div class='tabbar'>
	<img src='~assets/img/icon/金十logo-蓝.png' class='logo' />
	
	<el-menu
	  :default-active="activeIndex2"
	  class="el-menu-demo"
	  mode="horizontal"
	  @select="handleSelect"
	  background-color="white"
	  text-color="black"
	  active-text-color="black"  >
	  <el-menu-item index="1">首页</el-menu-item>
	  <el-menu-item index="2">数据</el-menu-item>
	  <el-menu-item index="3">资讯</el-menu-item>
	  <el-menu-item index="4">视频</el-menu-item>
	  <el-menu-item index="5">日历</el-menu-item>
	</el-menu>
	
	<el-dropdown class='tabbar-left' v-if="screenWidth<1240" >
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
	
	<div class='right'>
		<img src='~assets/img/icon/ic搜索.png'  class='serach'/>
		<el-tag effect="plain" class="load" size="medium">下载app</el-tag>
		<el-tag  effect="dark" class='load-right'size="medium">&nbsp&nbsp登录/&nbsp&nbsp注册 </el-tag>
		
	</div>
	
	</div>
</template>

<script>
	export default{
		name:'tabbarPc',
		props:{
			screenWidth:{
				type:Number,
				default:0
			}
		},
		data() {
		      return {
		        activeIndex: '1',
		        activeIndex2: '1'
		      }
		    },
		    methods: {
		      handleSelect(key, keyPath) 
			  {
		        console.log(key, keyPath);
		      }
		    }
	}
	
</script>

<style scoped="scoped">
	.tabbar{
		width: 100%;
		display: flex;
		text-align: center;
		background-color: white;
	}
	.logo {
		width: 128px;
		height: 32px;
		margin-top: 15px;
		margin-left: 21%;
		margin-right: 75px;
	}
	.right{
		position: absolute;
		right: 200px;
	}
	
	@media screen and (max-width: 1297px) {
			.right {
				position: relative;
			}
			
			.load{
				position: absolute;
				right: -88px;
				top: 18px;
				cursor: pointer;
			}
			.load-right{
				position: absolute;
				right: -158px;
				top: 18px;
				cursor: pointer;
			}
			
		}
		
		@media screen and (max-width: 1241px) {
				.el-menu-demo{
					display: none;
				}
				.logo{
					margin-left: 27%;
				}
			}
			
			
			@media screen and (max-width: 800px) {
					.load{
						right: -302px;
					}
					.load-right{
						right: -364px;
					}
					.serach{
						position: absolute;
						left: -187px;
					}
					.tabbar-left{
						margin-left: -38px;
					}
					
					
					
				}
		
		
		
		
		
		
		
		
	.serach{
		cursor: pointer;
		width: 17px;
		height: 17px;
		margin-top: 22px;
		margin-right: 20px;
		margin-left: 335px;
		margin-bottom: -3px;
	}
	.load{
		margin-right: 25px;
		cursor: pointer;
	}
	.load-right{
		cursor: pointer;
	}
	.el-menu-demo{
		z-index: 9;
	}
	
	
	
	.el-menu-vertical-demo:not(.el-menu--collapse) {
	    width: 200px;
	    min-height: 400px;
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
		/* position: absolute; */
		  /* left: 85px; */
		  background-color: white;
		  z-index: 9;
		  margin-top: 7px;
		 
		}
	
	
</style>
