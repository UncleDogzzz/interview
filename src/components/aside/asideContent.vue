<template>
	<div class="aside" >
		<!-- <div class='aside-top-imgage'>
			<div class='aside-top-image-image'><img src="~assets/img/icon/头像-2.png" /></br>
			</div>
			<div class='aside-top-name' >Skr橙子</div>
			<div class='aside-top-sign'>我是来自异次元的橙子</div>
			<div class='aside-top-number'>文章：320</div>
		</div> -->
		<aside-top-image />	
		<aside-top-recommend :scrollTop='scrollTop'/>
		
	</div>
</template>

<script>
	import asideTopImage from './childrenCom/asideTopImage.vue'   //侧边栏头像部分
	import asideTopRecommend from'./childrenCom/asideTopRecommend.vue'  //推荐栏部分
	export default{
		name:'asideContent',
		components:{
			asideTopImage,
			asideTopRecommend
		},
		props:{
			scrollTop:{
				type:Number,
				default:0
			}
		}
	}
</script>

<style>
	.aside{
		margin-top: 73px;
	}
	
	
	
</style>
