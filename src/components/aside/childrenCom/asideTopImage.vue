<template>
	<div class='aside-top-imgage'>
		<div class='aside-top-image-image'><img src="~assets/img/icon/头像-2.png" /></br>
		</div>
		<div class='aside-top-name' >Skr橙子</div>
		<div class='aside-top-sign'>我是来自异次元的橙子</div>
		<div class='aside-top-number'>文章：320</div>
	</div>
</template>

<script>
	export default{
		name:'asideTopImage'
	}
</script>

<style>
	.aside-top-imgage{
		background-color: #FFFFFF;
		height: 253px;
		text-align: center;
	}
	.aside-top-imgage img{
		width: 86px;
		height: 86px;
	}
	.aside-top-image-image{
		padding-top: 23px;
	
	}
	.aside-top-name{
		margin-top: 6px;
		font-weight: 500;
		font-size: 20px;
		
	}
	.aside-top-sign{
		margin-top: 6px;
		color: #898989;
		
	}
	.aside-top-number{
		width: 100px;
		border: #888888 solid 2px;
		margin-top: 16px;
	    margin-left: 110px;
		border-radius:5%;
		color: #898989;
		padding-top: 3px;
		padding-bottom: 3px;
		text-align: center;
	}
</style>
