<template>
	<div class='recommend' :class="{'recommend-flexd':sss}">
		<div class='recommend-title'>
			<div class='recommend-ttile-left'>推荐阅读</div>
			<div class="recommend-title-right" >查看更多
			
			<div class="triangle"></div>
			
			</div>
			</br>
		</div>
		<div class="recommend-content">
			<img src='~assets/img/content/图片-1.jpg'  class="recommend-title-img"/>
			<div class="recommend-content-text">
				<span class='recommend-item-title-span'>挂单报告：黄金留意下方空单押注元祐上行阻力分布密集</span>
			<div class="recommend-content-time">2小时前     <!-- time -->
			<span  class="author">喵呜</span>             <!-- 作者 -->
			</div>	
				
				
			<div class="split2"></div>         <!-- 分割线 -->
				
				
			<!-- <div class='recommend-item'>
				<img src='~assets/img/content/图片-2.jpg' />
				<div class="recommend-item-title"><span class='recommend-item-title-span'>黄金下方空单押注上行阻力分布</span>
				
				<div class="recommend-content-time">
					6小时前                                <!-- time -->
					<!-- <span  class="author-item">黄金圈</span>    <!-- 作者 -->
				<!-- </div>
				</div>
				<div class="split"></div> -->        <!-- 分割线 -->
			<!-- </div> -->
			
		<!-- <div class='recommend-item'>
			<img src='~assets/img/content/图片-3.jpg' />
			<div class="recommend-item-title"><span class='recommend-item-title-span'>黄金下方空单押注上行阻力分布</span> -->
			
			<!-- <div class="recommend-content-time">
				昨天                                <!-- time -->
				<!-- <span  class="author-item">技术刘</span>    <!-- 作者 -->
			<!-- </div>
			</div> -->
			<!-- <div class="split"></div> -->        <!-- 分割线 -->
		<!-- </div> -->
			
			
			<!-- <div class='recommend-item'>
				<img src='~assets/img/content/图片-4.jpg' />
				<div class="recommend-item-title"><span class='recommend-item-title-span'>黄金下方空单押注上行阻力分布</span>
				
				<div class="recommend-content-time">
					6月6日                               <!-- time -->
				<!-- 	<span  class="author-item">金融资讯</span>    <!-- 作者 -->
				<!-- </div>
				</div>
				<div class="split"></div>         <!-- 分割线 -->
			<!-- </div> --> 
			
		<!--	<div class='recommend-item'>
				<img src='~assets/img/content/图片-5.jpg' style="margin-bottom: 31px;" />
				<div class="recommend-item-title"><span class='recommend-item-title-span'>黄金下方空单押注上行阻力分布</span>
				
				<div class="recommend-content-time">
					6月5日                               <!-- time -->
					<!-- <span  class="author-item">技术刘</span>    <!-- 作者 -->
				<!-- </div>
				</div> -->
			<!-- </div> --> 
			
			
			
			<table>
				<tr>
				<td> <img src='~assets/img/content/图片-2.jpg' /> </td>	<td> 
				<div class='foot-top-title'>黄金下方空单押注上行阻力分布</div>
				 <div  class='foot-title'><span style="margin-left: 10px;">6小时前   </span>                              <!-- time -->
				 	<span class='span11' >黄金圈</span>    <!-- 作者 -->
				 </div>
				 </td>
					</tr>
					<div class="split"></div>
					
					
					<tr>
					<td> <img src='~assets/img/content/图片-3.jpg' /> </td>	<td> 
					<div class='foot-top-title'>黄金下方空单押注上行阻力分布</div>
					 <div  class='foot-title'><span style="margin-left: 10px;">昨天 </span>                              <!-- time -->
					 	<span class='span11' >技术刘</span>    <!-- 作者 -->
					 </div>
					 </td>
						</tr>
						<div class="split"></div>
						
						
						<tr>
						<td> <img src='~assets/img/content/图片-4.jpg' /> </td>	<td> 
						<div class='foot-top-title'>黄金下方空单押注上行阻力分布</div>
						 <div  class='foot-title'><span style="margin-left: 10px;">6月6日 </span>                              <!-- time -->
						 	<span class='span11' >金融资讯</span>    <!-- 作者 -->
						 </div>
						 </td>
							</tr>
							<div class="split"></div>
							
							
						<tr>
						<td> <img src='~assets/img/content/图片-5.jpg'/> </td>	<td> 
						<div class='foot-top-title'>黄金下方空单押注上行阻力分布</div>
						 <div  class='foot-title'><span style="margin-left: 10px;">6月6日 </span>                              <!-- time -->
						 	<span class='span11' >金融资讯</span>    <!-- 作者 -->
						 </div>
						 </td>
							</tr>
							<div class="split1"></div>	
							
							
							
							
							
						
						
						
					
			</table>
			
			
			
			
			
			
			
			
			
			
		</div>
	
			
		</div>
		
		<!-- <aside-back-top /> -->
	</div>
</template>

<script>
	import asideBackTop from './asideBackTop.vue'          //返回顶部
	export default{
	name:'asideTopRecommend',
	props:{
		scrollTop:{
			type:Number,
			default:0
		}
	},
	computed:{
		sss(){
			return this.scrollTop>343;
		}
	},
	components:{
		asideBackTop
	}
	}
</script>

<style>
	.recommend{
		background-color: #FFFFFF;
		margin-top: 34px;
		padding-top: 18px;
		padding-left: 17px;
		width: 301px;
		margin: auto;
	}
	.recommend-title{
		
		position: relative;
		height: 100%;
		margin-left: 17px;
	}
	.recommend-ttile-left{
		position: absolute;
		left: -7px;
		font-size: 21px;
		font-weight: 600;
	}
	.recommend-title-right{
		position: absolute;
		right: 28px;
		font-size: 13px;
		padding-top: 8px;
		cursor:pointer;
		color: #8a8a8a;
		padding-right: 9px;
	}
	.triangle{
		border-style: solid;
		border-width: 10px 0px 10px 10px;
		transform: rotate(-45deg);
		 border-color: transparent transparent #888888 transparent;
		 width: 0px;
		 height: 0px;
		 position: absolute;
		 top: 4px;
		 right: -5px;
	}
	.recommend-title-img{
		width: 272px;
		height: 146px;
		margin-top: 27px;
		margin-left: 12px
	}
	.recommend-content-text{
		margin-left: 11px;
		margin-top: 14px;
		margin-right: 23px;
		letter-spacing:0px;
	}
	
	.recommend-content-time{
		color:#979797;
		margin-top: 8px;
		position: relative;
		font-size: 14px;
		
	}
	.author{
		position: absolute;
		right: -5px;
	}
	.author-item{
		position: absolute;
		right: 13px;
	}
	.split{
		width: 248%;
		height: 1px;
		border-top: solid #efefef 2px;
		margin-top: 22px;
	}
	.recommend-item{
		margin-top: 24px;
		position: relative;
	}
	
	.recommend-item img{
		width: 107px;
		height: 70px;
		margin-bottom: 3px;
	}
	.recommend-item-title{
		position: absolute;
		right: -17px;
	    width: 206px;
		top: -2px;
	}
	.recommend-item-title-span{
		font-size: 14px;
		cursor: pointer;
	}
	.recommend-item-time{
		color:
	}
	
	@media screen and (max-width: 500px) {
			/* .recommend-title-img{
				width: 283px;
				height: 134px;
				margin-top: 27px;
				margin-left: -34px;
			}
			
			.recommend-content-text{
				margin-left: -34px;
				margin-top: 14px;
				margin-right: 23px;
			}
			
			.recommend-item-title{
				position: absolute;
				right: -44px;
			    width: 206px;
				top: -2px;
			} */
			.recommend{
				width: 301px;
			}
			
			.recommend-title{
				margin-left: 17px;
			}
			
			.recommend-content{
				margin-left: 0px;
			}
			
		}
		
		@media screen and (max-width: 653px) {
				.recommend{
					width: 222px;
				}
				.recommend-title{
					margin-left: -47px;
				}
				.recommend-content{
					margin-left: -64px;
				}
				.author{
					right: -20px;
				}

			}
			
			/* @media screen and (max-width: 500px) {
					.recommend{
						width: 222px;
					}
					.recommend-title{
						margin-left: -47px;
					}
					.recommend-content{
						margin-left: -64px;
					}
					
					
					
				} */
		
		
		
		
		
		
		
		
	.recommend-flexd{
		
		position: fixed;
		top: 68px;
	}
		
	
	
	
	td img{
		width: 104px;
		height: 60px;
		margin-top: 16px;
	}
	.foot-title{
		color: #979797;
		font-size:12px ;
		margin-top: -10px;
		margin-bottom: 2px;
		position: relative;
	}
	.foot-top-title{
		font-size: 14px;
		cursor: pointer;
		margin-bottom: 20px;
		margin-top: 13px;
		margin-left: 9px;
		width: 166px;
		
	}
	.span11{
		cursor: pointer;
	    position: absolute;
	    right: 15px;
		
	}
	table{
		border-collapse: separate;
		border-spacing: 3px 3px;
	}
	
	.split1{

		margin-top: 22px;
	}
	.split2{
		width: 100%;
		height: 1px;
		border-top: solid #efefef 2px;
		margin-top: 22px;
	}
	
</style>
