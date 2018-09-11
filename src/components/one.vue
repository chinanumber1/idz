<template>
 <div id="bottom"> 
   


      
<div  v-if="step1" class="index_button">


<div v-if="stepunactive1">
<button class="step_one">在下面选择款式</button>
<dialogBar></dialogBar>
</div>

			<div v-else class="step_arrow" v-show="step_shows">

							<div style="display:flex">
								<div style="width:20%;text-align: right">

								</div>
								<div style="width:60%">
									<a @click="">
										<button class="step_two">下一步选择面料</button>
									</a>
								</div>
								<div style="width:20%;text-align: left">
								 <router-link to="/two">	<img style="margin-top:1.2rem" src="../assets/arrow.png" width="1027" height="1063" alt="" class="arrow" /></router-link>
									
								
								</div>
							</div>
						</div>



  <div class="sub" v-html="content">


  </div>


</div>


  <div id="style">

    <ul class="style">

    <li v-for="(item,index) in cloths" :key="index" @click="changeCloth(index)" class="change" :class="{boxactive:item.active}">
				<div class="meter"> <img :src="item.img" /></div>
      
				</li>

         
    
    </ul>

    </div>


  



 


    
     </div>
     


</template>


<script>
import dialogBar from "./dialog";

export default {
    
  name: "App",
components: {

   dialogBar

  },

  
  data() {
    return {
      step1: true,
step_shows:false,
stepunactive1:true,

      cloths: [

      ],
       content: '款式搜索 <img src="../static/so.svg"> 款式搜索',

    }
  },

  mounted() {
        var arr = [];
        for (var i = 0; i < 16; i++)
          arr.push({ img: "../static/cloth.png",active: false });
        console.log(arr)
        this.cloths = arr;
      },


  methods: {
        changeCloth: function(_idx) {
          var data = this.cloths;
          for (var i = 0; i < data.length; i++) {
            if (_idx == i) {
              data[i].active = true;
            } else {
              data[i].active = false;
            }
          }
          

          this.cloths = data;
         this.stepunactive1 = false;
         this.step_shows = true;

        }

      }
      
};



</script>


<style>

.arrow {
    width: 2rem;
    height: auto;
}

 .step_one {
    height: auto;
    background-color: #e3e4e6;
    line-height: 3rem;
    text-align: center;
    color: #fff;
    font-size: 1.5rem;
    cursor: pointer;
    position: relative;
    z-index: 100;
    border: none;
    margin: auto;
    padding-left: 2rem;
    padding-right: 2rem;
    width: 15rem;
    border-radius: 3rem;
  }
  .step_two{
    height: auto;
    background-color: #da251d;;
    line-height: 3rem;
    text-align: center;
    color: #fff;
    font-size: 1.5rem;
    cursor: pointer;
    position: relative;
    z-index: 100;
    border: none;
    margin: auto;
    padding-left: 2rem;
    padding-right: 2rem;
    width: 15rem;
    border-radius: 3rem;
  }

  .meter img {
    width: 100%;
}

.sub img{
    width: 1rem;
}
</style>


