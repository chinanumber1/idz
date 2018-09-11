<template>
<div class="sidebar" id="stepline">

				<ul class="math">
					<li class="round" :class="{unactive:active1}">1</li>
					<li>
						<div class="line" ></div>
					</li>
					<li class="round" :class="{unactive:active2}">2 </li>
					<li>
						<div class="line_two"></div>
					</li>
					<li class="round" :class="{unactive:active3}">3</li>


				</ul>

			</div>

            </template>

            <script>
export default {
  name: 'stepline',
  data () {
    return {
		active1: false,
			active2: false,
			active3: false
			
    }
	},
	methods:{

				activeStep1: function () {
				this.active1 = true;
				this.active2 = false;
				this.active3 = false;
			},
			activeStep2: function () {
				this.active1 = true;
				this.active2 = true;
				this.active3 = false;
			},
			activeStep3: function () {
				this.active1 = true;
				this.active2 = true;
				this.active3 = true;
			}

	}
	
 

}
</script>

<style>


  .sidebar{
    position: absolute;
    right: 1rem;
    top: 1rem;
  }
  .sidebar li{
      list-style:  none;
  }

  .round{
    width: 3.5rem;
    height: 3.5rem;
    line-height: 3.5rem;
    color: #fff;
    background: #e3e4e6;
    border-radius: 50%;
    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    text-align: center;
    list-style: none;
    font-weight: bold;
    position: relative;
    z-index: 2;
	}
	
	.line{
    width: 1px;
    background: #aaa9a9;
    height: 5rem;
    position: absolute;
    right: 1.7rem;
    bottom: 10rem;
    z-index: 1;
}

.math li {
    margin-top: 3.5rem;
    list-style: none;
}


.line_two {
    width: 1px;
    background: #aaa9a9;
    height: 5rem;
    position: absolute;
    right: 1.7rem;
    bottom: 3rem;
    z-index: 1;
}

.unactive {
		background-color: #2ca3f3;
		
}


</style>
