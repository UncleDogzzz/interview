<template>
	<div class='text-content-video' >          <!-- 文章内容视频栏 -->
		<video width="100%" height="100%"  poster="~assets/img/content/视频.jpg"  id='video' >
			<source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4">
		 </video>
		 
		<img src="~assets/img/icon/ic播放.png" class="play" @click='play2' v-if='!isShowConC'/>
		<img src="~assets/img/icon/ic暂停.png" class="play" @click='play2' v-if='isShowConC'>
		 
		 <div class="controls">
		                <img src="~assets/img/icon/ic暂停.png" id="play"  @click='play' v-if="isShow"/>
						<img src="~assets/img/icon/ic播放.png" id="play" @click='play' v-else/>
		                <!-- <img src="~assets/img/icon/ic快退.png" id="back" @click='back'/>
		                <img src="~assets/img/icon/ic快进.png" id="speed"  @click='speed'/> -->
		                
		               <!-- <img src="~assets/img/icon/声音.png" id="mute" @click="mute" v-if="isShowSouce"/>
						 <img src="~assets/img/icon/ic静音.png" id="mute" @click="mute" v-if="!isShowSouce"/> -->
		                
						<span style="position: absolute;top: 9px;left: 34px;color: #5077E1;">进度：</span><div id="rangebar"> <p></p> </div>
						<!-- <span id='totall'> </span> -->
						<img src="~assets/img/icon/ic画质.png" class='quary' @click="quaryClick"/>&nbsp&nbsp&nbsp&nbsp
						
						<span class='quary-span'>超清 </span>
						
		                <img src="~assets/img/icon/声音.png" id="mute" @click="mute" v-if="!isShowSouce"/>
		                <img src="~assets/img/icon/ic静音.png" id="mute" @click="mute" v-if="isShowSouce"/> 
						<input type="range" id="progress" value="30" min="0" max="100" />
					<img src="~assets/img/icon/ic全屏.png"  id="fullscreen" @click="fullscreen"/>
		            </div> 
		 
	
	</div>
	
	
</template>

<script>
	export default{
		name:'contentVideo',
		methods:{
			play(){
				if(video.paused){                  //播放or暂停
				    video.play()
					}
					else{
						video.pause()
					}
					this.isShow=!this.isShow;
					this.isShowConC=!this.isShowConC;
					// console.log(this.isShowConC)
					if(this.isShowConC){
						setTimeout(()=>{
						document.getElementsByClassName('play')[0].style.display='none';
						},1000)
					}
					else{
						document.getElementsByClassName('play')[0].style.display='block';
					}
			},
			play2(){
				if(video.paused){                  //播放or暂停
				    video.play()
					}
					else{
						video.pause()
					}
					this.isShow=!this.isShow;
					this.isShowConC=!this.isShowConC;
			},
			fullscreen(){                     //全屏
				let element = document.getElementById('video')
				 this.Screen(element)
			},
			back(){                          //快退
				this.video.currentTime -= 5;
			},
			speed(){                        //快进
				this.video.currentTime += 5;
			},
			mute(){                     //静音or开启声音
				this.video.muted = !this.video.muted;
				this.isShowSouce=!this.isShowSouce;
				if(this.video.muted){
				document.getElementById('progress').value=0;
				}
				else{
					document.getElementById('progress').value=this.video.volume*100
				}
			},
			quaryClick(){
				// console.log(123);
				// document.getElementById('video').requestPictureInPicture();
			}
			},
		data(){
			return{
				isShow:false,
				isShowConC:false,
				video:null,     //video对象
				Screen:null,    //全屏函数
				timer:null,
				isShowSouce:false
			}
		},
		destroyed() {
			clearInterval(this.timer);
		},
		
		mounted(){

			 this.Screen=function Screen (element) {                //进入全屏函数
			        if (element.requestFullscreen)  {
			            element.requestFullscreen();
			        } else if (element.mozRequestFullScreen) {
			            element.mozRequestFullScreen();
			        } else if (element.msRequestFullscreen) {
			            element.msRequestFullscreen();
			        } else if (element.oRequestFullscreen) {
			            element.oRequestFullscreen();
			        } else {
			            element.webkitRequestFullScreen();
			        }
			    
			}
			
			this.video = document.getElementsByTagName("video")[0];
			var _this=this;
			
			document.getElementsByClassName('text-content-video')[0].onmouseover=function(){
				document.getElementsByClassName('play')[0].style.display='block';
				document.getElementsByClassName('controls')[0].style.display='block';
			}
			document.getElementById('video').onmouseout=function(){
				document.getElementsByClassName('play')[0].style.display='none';
				document.getElementsByClassName('controls')[0].style.display='none';
			}
			document.getElementById('video').onclick=function(){
				if(document.getElementById('video').paused){                  //播放or暂停
				    document.getElementById('video').play()
					}
					else{
						document.getElementById('video').pause()
					}
					_this.isShow=!_this.isShow;
					_this.isShowConC=!_this.isShowConC;
			}
			
			
			
			this.timer = setInterval(function(){                             //获取视频进度
			  
			   document.getElementById('rangebar').getElementsByTagName("p")[0].style.width=(video.currentTime/video.duration)*100+'%';
			   // console.log((video.currentTime/video.duration)*100+'%')
			},100)
			
			this.video.oncanplay = function() {           //视频加载完成后，获取总时长。设置初始化声音大小
			 
                // document.getElementById('totall').innerHTML = '  时长:  '+parseInt(video.duration)+'秒';  //总时长
				 video.volume = document.getElementById('progress').value/100;     //初始化声音
			}
			
		   document.getElementById('progress').onmousemove = function(){               //调节声音大小
		                video.volume = document.getElementById('progress').value/100;
		            }
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			// document.getElementById('fullscreen').onclick=function()   //全屏
			// {  
			// 	   let element = document.getElementById('video')
			// 	        Screen(element)
			// }
			
			
			
			
	   
		}
	}
	
	
	
	           
	            
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
</script>

<style>
	.text-content-video{
		position: relative;
	}
	
	.controls{
		position: absolute;
		bottom: 3px;
		color:#000000;
		width: 100%;
		background-color: #333333;
		height: 32px;
	}
	input[type="button"]{
	               background-color: cornflowerblue;
	               color: #fff;
	               border: none;
	               padding: 5px 10px;
	               cursor: pointer;
	           }
	#rangebar {
	                width: 13%;
	                height: 5px;
	                border: 1px solid #ccc;
	                margin-top: 3px;
	                position: absolute;
	                top: 15px;
	               left: 75px;
	               
					
					
	            }
	#rangebar>p {
				     width: 0%;
				     height: 100%;
				     background-color: blueviolet;
					 margin-top: 0px;
				}
				
		img  {
			cursor: pointer;
			margin-top: 2px;
		}
	#totall{
		margin-left: 101px;
	}	
	#fullscreen{
		position: absolute;
		right: 3px;
		top: 5px;
		
	}	
	#progress{
	   top: 9px;
	   width: 10%;
	   position: absolute;
	   right: 3%;
	}
	
	#play{
		margin-bottom: -6px;
		position: absolute;
		top: 0px;
		left: 0px;
	}
	#speed {
		position: absolute;
		top: 0px;
		left: 76px;
		width: 37px;
		height: 35px;
		
	}
	#back{
		position: absolute;
		top: 0px;
		left: 39px;
		width: 37px;
		height: 35px;
	}
	#mute{
		width: 37px;
		height: 35px;
		position: absolute;
		top: 1px;
		right: 14%;
	}
	
	.quary{
		width: 32px;
		height: 26px;
		position: absolute;
		top: 6px;
		right: 34%;
		
	}	
	
	.play{
		position: absolute;
		top: 40%;
		left: 50%;
		cursor: pointer;
	}
	.voice{
		margin-left: 22px;
		margin-bottom: -1px;
	}
	.quary-span{
		position: absolute;
		right: 29%;
		top: 12px;
	}
	
	
	
	/* @media screen and (max-width: 1241px) {
			#mute{
				right: 17%;
			}	
		} */
		@media screen and (max-width: 1646px) {
				#mute{
					right: 20%;
				}
				#progress{
					right: 8%;
				}	
			}
			@media screen and (max-width: 1538px) {
					.quary-span{
						
						right: 28%;
						
					}
				}
				
			@media screen and (max-width: 1143px) {
					.quary-span{		
						right: 31%;
					}
					.quary{
						right: 40%;
					}
				}	
				
				
				
				
				
				
				
				
				@media screen and (max-width: 949px) {
						.quary-span{
							right: 35%;
							
						}
						.quary{
							right: 48%;
						}
					}
					@media screen and (max-width: 400px) {
							.quary-span{
								display: none;
								
							}
							.quary{
								display: none;
							}
						}
	
	
	
	/* canvas{
		width: 78%;
		height: 100%;
	} */
	
	
		
</style>
