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
html,body{
    /* 100px=26.67vw */
    font-size: 26.67vw;
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
</style>
