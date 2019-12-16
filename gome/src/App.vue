<template>
  <div id="app">
    
    <router-view></router-view>
  </div>
</template>

<script>


export default {
  name: 'app',
  components: {}
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  #app{
    height: 100%;
  }
html,body{
    /* 100px=26.67vw */
    font-size: 26.67vw;
    height: 100%;
}
a{
  text-decoration: none;
}
ul,li{
  list-style: none;
}
.el-carousel__indicators--vertical {
   
    display: none;
} 
.el-carousel__container {
    position: relative;
    height: 1.235rem!important;
}
.el-carousel__arrow{
    display: none!important;
}
</style>
