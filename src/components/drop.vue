	<template>
    <div id="page">
			<div id="dialog-face" class="dialog-face" rel="DialogFace" v-show="isMark">
			</div>





			<div id="dialog" class="dialog-root" v-show="isShow">
				<div id="dialog-wrapper" class="dialog-wrapper">


				
            <div class="dialog-header">
                <span></span>
            </div>
		

					<div class="dialog-content">

						<img src="../assets/drop.png" />


					</div>
					<div class="dialog-footer">
						<button v-on:click="toggle()">开始你的设计</button>
					</div>
				</div>
			</div>

		</div>
        
 </template>

 <script>
export default {
  name: 'Page',
  data () {
    return {
      isShow: true,
      isMark:true
    }
  },

 methods:{

   
            
   toggle: function(){
 this.isShow = !this.isShow;
this.isMark = !this.isMark;


   }
  }
}


</script>

<style>
/* ---------------------弹窗样式 -------------------*/
        /* 遮挡层样式 */
        .dialog-face{
            position: fixed;
            background: #000;
            height: 100%;
            width: 100%;
            z-index: 1000;
            top: 0;
            left: 0;

            opacity: 0.7;
        }
        /* 弹窗布局样式 */
        .dialog-root{
            position: fixed;
            z-index: 2000;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
			width:  80%;
			
				 /* background:url(images/drop.png) no-repeat;
				background-size:contain;*/
			
        }
        /* 弹窗容器 */
        .dialog-wrapper{
        
          
            height: auto;
            overflow: hidden;
            -webkit-border-radius: 5px;
            -moz-border-radius: 5px;
            border-radius: 5px;
			text-align: center;
			
		
			
			
        }
        /* 弹窗标题 */
        .dialog-header{
            height: 75px;
            text-align: center;
        }

        .dialog-header span{
            font-size: 28px;
            line-height: 75px;
            color:#F6CBC6;
        }
        /* 弹窗内容 */
        .dialog-content{
            
        }
		
		.dialog-footer{
			text-align: center;
    position: relative;
	bottom: 2rem;
	cursor: pointer;
		
		}

        .dialog-content p{
            margin: 0;
            padding: 10px 0;
        }
		
		  .dialog-content img{
		  background-size:contain;
				width:  80%;
		  }


</style>