<template>
	
	<div class='content' :class="{'phone-content':sss}">
	  <div class='zrh'>
		  <div class="title">                            <!-- 标题栏 -->
		  	<span >挂单报告：黄金上方助力明显，欧美下方有密集支撑</span>
			</div>
			
		  <div class='title-img'>                                 <!-- 标题头像栏 -->
			  <div class='title-left' >
			  <img src='~assets/img/icon/头像.png' class='head-img' />
			  <span class='title-left-span'>Skr橙子</span> 
			  <span class='title-left-span-time'>  ·  1小时前</span>
			  </div>
			  <div class='title-utils'>                  <!-- 标题头像工具栏 -->
	

			  
				  <span class='title-left-span-time' v-if="screenWidth>599" >生成图片</span>
				  <span class='title-left-span-time' v-if="screenWidth<500&&screenWidth>392" >生成图片</span>
				  <img src='~assets/img/icon/ic生成图片.png' class='poto' v-if="screenWidth>335" />
				  
				  <span class="link-right" v-if="screenWidth>912"></span>
				  <span class='title-left-span-time' v-if="screenWidth>912">分享文章</span>
				  <a href='http://service.weibo.com/share/share.php?title=分享的内容&url=分享的地址&pic=分享的图片' target="_blank" >
				  <img src='~assets/img/icon/ic微博.png' v-if="screenWidth>912" class='icon' />
				  </a>
				  <a href='https://sns.qzone.qq.com/cgi-bin/qzshare/cgi_qzshare_onekey?title=分享标题&url=分享的地址&summary=分享的摘要&pics=分享的图片' target="_blank" >
				  <img src='~assets/img/icon/icQQ.png' v-if="screenWidth>912" class='icon' />
				  </a>
				  
				  <el-dropdown v-if="screenWidth>912">
				        <span class="el-dropdown-link">
				          <img src='~assets/img/icon/ic微信.png' v-if="screenWidth>912" class='icon'/>
				        </span>
				        <el-dropdown-menu slot="dropdown" style="text-align: center;">
				         <h4> 打开微信扫一扫</h4>
				          <img src='~assets/img/icon/ic二维码.png' class="code"/>
				        </el-dropdown-menu>
				      </el-dropdown>
				  
				  
				
			  </div>
		  </div>
		  
		  
		  <div class='text-content'>                           <!-- 文章内容栏 -->
			<p style="margin-bottom: 38px;"> 关注挂单报告，从市场的筹码分布出发，解读挂单背后的多空秘密。主要覆盖品种：黄金、原油、英镑、欧元、日元、加元、澳元。数据均来自大型经纪商，仅供参考，不作投资建议。</p>
			<p>标普500指数年内迄今已上涨了逾10%，不过涨势在最近几周却陷入停滞，因交易员们在经济增长前景与通胀威胁间陷入权衡。从石油到木材的原材料成本大幅上升、供应链出现瓶颈、劳动力市场趋紧等诸多现象，均加剧了人们对通胀过热的担忧。</p>
		  </div>
		  
		  <div class="text-content-image">         <!-- 文章内容走势图片栏 -->
			 <div class='text-content-image-title'>
				 近一年黄金走势
			 </div>
			 
			 <div class='text-content-image-detail'>
			 	<content-view  ref='contentView'/>                        <!-- 数据图表 -->
			 </div>

			 <div class='text-content-image-detail-more'>
			 	<strong>由于头部正极材料企业往往与下游动力电池大厂深度绑定，产有所供，能维持较高的产能利用率，而尾部企业销量少，难盈利，整个行业马太效应进一步凸显。</strong>
			 </div>
		  </div>

		  <content-video />               <!-- 视频栏 -->
		  
	 <div class='foot-text'>          <!-- 底部文字 -->
		 <div class='foot-text-content'>
			 <p>标普500指数年内迄今已上涨了逾10%，不过涨势在最近几周却陷入停滞，因交易员们在经济增长前景与通胀威胁间陷入权衡。从石油到木材的原材料成本大幅上升、供应链出现瓶颈、劳动力市场趋紧等诸多现象，均加剧了人们对通胀过热的担忧。</p>
		 </div>
		 <div class='foot-content'>
			<p> 申明：</p>本文版权归金十数据所有，未经书面授权任何商业机构、网站、公司及个人禁止转载或再利用文中信息，违者必究
		 </div>
		 
		 
	 </div>
			
	 <div class='foot'>                                  <!-- 底部栏 -->
	 <div class='foot-co'>
		 <div class='cicle'>
		<img src="~assets/img/icon/ic点赞.png" /></br>
		<div class="cicle-font">46 </div>
		</div>
		<div class='foot-font'><span>好文章，需要你的鼓励</span></div>
		</div>
	 </div>	  
	  <slot ></slot> 
	  </div>
	</div>
	
	
</template>

<script>
	import contentVideo from './childrenCom/contentVideo.vue'          //视频组件
	import contentView from './childrenCom/contentView.vue'      //数据图组件
	export default{
		name:'textcontent',
		components:{
			contentVideo,
			contentView
		},
		props:{
			screenWidth:{
				type:Number,
				default:0
			},
			screenWidth:{
				type:Number,
				default:0
			}
		},
		computed:{
			sss(){
				return this.screenWidth<500;
			}
		},
		methods:{
			ImgClick(){
				console.log(213);
				this.isshow=!this.isshow
				
			}
		},
		data(){
			return{
				isshow:true
			}
		},
		mounted() {
	
		
	}
	}
	
</script>

<style>
	.content{
		position: relative;
		width: 78%;
		height: 100%;
	
	
		
		background-size:90px 30px;
		background-repeat: repeat;
		overflow-x: hidden;
		margin-left: 25%;
		
		
	}
	.title{
	
	}
	
	
	.title span{
		font-size: 21px;
		font-weight: bold;
	}
	
	/* .title-left{
		position: absolute;
		left: 3px;
	}
	.title-left img{
		width: 23px;
		height: 25px;
		margin-top: 20px;
		margin-bottom: -5px;
	} */
	.title-left-span{
		color:#6285e4;
		margin-left: 15px;
	}
	.title-left-span-time{
		color:#959595;
	}
	
	.title-left-right{
		position: absolute;
		top: 68px;
		left: 360px;
	}
	
	.zrh{
		margin-top: 72px;
		margin-left: 32px;
		margin-right: 38px;
		background-color: #FFFFFF;
		padding-top: 31px;
		padding-left: 36px;
		padding-right: 3px;
		
		background-image: url('~assets/img/content/水印.png');
		background-size:157px 150px;
			
	}
	
	.head-img{
		width: 23px;
		height: 25px;
		margin-bottom: -5px;
		
	}
	.title-img{
		margin-top: 22px;
		position: relative;
	}
	
	.title-utils{
		position: absolute;
        right: 3px;
		top: 3px;
		font-size: 13px;
	}
	.title-left{
		display: inline-block;
	}
	
	.poto{
		width: 14px;
		height: 12px;
		margin-left: 9px;
		margin-right: 13px;
	}
	
	@media screen and (max-width: 500px) {
			
			.poto{
				margin-right: 0;
			}
			
			
			
		}
	
	
	.link-right {
	    width: 50px;
	    height: 20%;
	    border-right: solid #ACC0D8 2px;
		margin-right: 11px;
	}
	
	.icon{
		width: 19px;
		height: 18px;
		margin-left: 9px;
		margin-right: 5px;
		margin-bottom: -3px;
	}
	
	.text-content{
		color: #7b7e8e ;
		font-size: 16px;
		letter-spacing:2px;
	}
	
	.text-content-image{
		margin-top: 50px;
	}
	
	.text-content-image-title{
		font-size: 18px;
		font-weight: bold;
	}
	
	.text-content-image-detail-more{
		color:#5077e1;
		font-weight: 500;
		margin-bottom: 47px;
		font-size: 16px;
		letter-spacing:2px;
		
	}
	.foot-text{
		margin-top: 50px;
	}
	.foot-text-content{
		color: #777a8b;
		letter-spacing: 1px;
	}
	.foot-content{
		color:#b2b2b2;
	}
	.foot{
		
	}
	
	
	.foot-co{
		position: relative;
		text-align: center;
	}
	
	
	
	
	
	
	
	.foot img{
		margin-left: 7px;
		margin-top: 17px;
		margin-bottom: 7px;
		width: 40px;
		height: 40px;
	}
	.cicle{
		border-radius: 50%;
		width: 100px;
		height: 100px;
		background-color:#ffffff;
		border: #efefef solid ;
		margin-bottom: 18px;
		margin: auto;
		margin-top: 87px;
		text-align: center;
			
	}
	.foot-font{
		color: #b2b2b2;
		margin-top: 15px;
		margin-bottom: 6px;
		padding-bottom: 41px;
	}
	.cicle-font{
		color: #b2b2b2;
		
	}
	
	.phone-content{
		margin-left: -18%;
		width: 123%;
	}
	
	.code{
		width: 100px;
		height: 100px;
		margin-bottom: -13px;
	}
	
</style>
