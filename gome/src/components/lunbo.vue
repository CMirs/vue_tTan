<template>
    <div class="lunbo">
            <el-carousel :interval="3000" arrow="hover" style="height: 1.1rem">
                    <el-carousel-item  v-for="(item,index) in images" :key="index">
                      <h3><img :src="item" style="width: 100%;"/></h3>
                    </el-carousel-item>
                  </el-carousel>
    </div>

</template>
<script>
export default {
    data(){
        return{
             images:[
      //   require求请求图片过来
      require("../assets/img/T1SGJQBCJ_1RCvBVdK_1080_320.webp"),
      require("../assets/img/T1oxxjBbD_1RCvBVdK_1080_320.webp"),
      require("../assets/img/T1pkhsBCAv1RCvBVdK_1080_320.webp"),
      require("../assets/img/T1PrhQBg_v1RCvBVdK_1080_320.webp")
      ]
        }
       
    }
}
</script>
<style scoped>
  .el-carousel__container{
  height:1.1rem!important;
}
.lunbo{
    height: 1.1rem;
}
  .el-carousel__item h3 {
    color: #475669;
    font-size: .18rem;
    opacity: 0.75;
    line-height: 1.1rem;
    margin: 0;
  }
  
  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }
  
  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
</style>