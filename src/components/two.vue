<template>
 <div id="bottom"> 


      
<div  v-if="step2" class="index_button">


<div v-if="stepunactive2">
		<div style="display:flex">
    		<div style="width:20%;text-align: right">
                  <router-link to="/">
<img src="../assets/arrow4.png" width="1027" height="1063" alt="" class="arrow" style="margin-top: 1.4rem; transform: rotate(180deg);">
                  </router-link>
    </div>
    
    <div style="width:60%">
<button class="step_one">在下面选择面料</button>
</div>
	<div style="width:20%;text-align: left">
<img src="../assets/arrow4.png" width="1027" height="1063" alt="" class="arrow" style="margin-top: 1.2rem;">
</div>
</div>

</div>

			<div v-else class="step_arrow" v-show="step_shows">

							<div style="display:flex">
								<div style="width:20%;text-align: right">
 <router-link to="/">
<img src="../assets/arrow.png" width="1027" height="1063" alt="" class="arrow" style="margin-top: 1.4rem; transform: rotate(180deg);">
 </router-link>	
                                </div>
								<div style="width:60%">
								 <router-link to="/three">
										<button class="step_two">下一步个性化DIY</button>
								</router-link>
								</div>
								<div style="width:20%;text-align: left">
								 <router-link to="/three">	<img style="margin-top:1.2rem" src="../assets/arrow.png" width="1027" height="1063" alt="" class="arrow" /></router-link>
									
								
								</div>
							</div>
						</div>



  <div class="sub" v-html="content"></div>


</div>


  <div id="style">

    <ul class="style">

   <li v-for="(item,index) in materials" :key="index" @click="changeMaterial(index)" class="change" :class="{boxactive:item.active}">
											<div class="meter"> <img :src="item.img" /></div>
		</li>

         
    
    </ul>

    </div>


 



 

    
     </div>
     


</template>


<script>

export default {
    
  name: "App",
  
  data() {
    return {
      step2: true,
step_shows:false,
stepunactive2:true,

   materials:[
       
   ],
       content: '款式搜索 <img src="../static/so.svg"> 款式搜索',
    }
  },

mounted() {
								var arr = [];
								for (var i = 0; i < 16; i++)
									arr.push({ img: '../static/mian.png', active: false });
								this.materials = arr;

							},

  methods: {

      changeMaterial: function (_idx) {
									var data = this.materials;
									for (var i = 0; i < data.length; i++) {
										if (_idx == i) {
											data[i].active = true;
										} else {
											data[i].active = false;
										}
									}

									this.materials = data;
                             this.stepunactive2 = false;
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


