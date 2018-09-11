<template>

  <div id="app">
 <Sidebar></Sidebar>

   <Drop></Drop>

    <div id="top">

    <Left></Left>
 

<div id="right">
      <img src="./assets/xifu.jpg" style="width: 100%">


    <div class="tab_content">


<ul class="nav_li">
      <li class="current_cloth"><a href="javascript:;">套西</a></li>
       <li><a href="javascript:;">单西</a></li>
        <li><a href="javascript:;">衬衫</a></li>
        
        </ul>
</div>


</div>

    </div>



   <router-view></router-view>



  </div>




  

</template>

<script>
import Left from "./components/left";
import Sidebar from "./components/sidebar";
import Drop from "./components/drop";
import One from "./components/One";

export default {
  name: "App",
  components: {
  Left,
   Sidebar,
   Drop,
   One,
 

  },


  data() {
    return {
      step1: true,
       message: '款式搜索款式搜索!',
    }
  },


  
      
};
</script>

<style>
.nav_li li {
    display: inline;
    list-style: none;
    font-size: 1.5rem;
}
.nav_li li a{
 color:#e25d5d;
 text-decoration: none;
}
</style>
