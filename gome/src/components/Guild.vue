<template>
    <div>
    <div class="main_1">
        <div class="usnew">
            <div class="u_top">
               <span>更多 >></span>
            </div>
            <div class="u_down">
                <ul>
                    <li>
                        <img src="../assets/img/T12HVbBT_v1RCvBVdK_354_242.jpg" alt="" style="height: 100%">
                    </li>
                    <li>
                        <p style="color:#48a6ff">有好货</p><span>今日好货</span><img
                            src="../assets/img/T19whvB_EQ1RCvBVdK_355_144.jpg" alt="">
                    </li>
                    <li>
                        <p >品类排行榜</p>
                           <dl>
                               <dt>近30天</dt>  
                              <dd>月销9.9万</dd>
                           </dl>
                    </li>
                    <li>
                        <el-carousel :interval="5000" arrow="always" >
                            <el-carousel-item v-for="(item,idx) in sales" :key="idx">
                              <h3><img :src="item" style="width:100%"></h3>
                            </el-carousel-item>
                          </el-carousel>
                    </li>
                </ul>
            </div>

        </div>
    </div>
    <div class="floor_good">
     <div class="floor_img">
        <ul>
            <li><img src="../assets/img/T17fdgBbCv1RCvBVdK_350_182.webp" alt=""></li>
            <li><img src="../assets/img/T1ISZQB5W_1RCvBVdK_350_182.webp" alt=""></li>
        </ul>
     </div>
    </div>
    <div class="main_2">
        <div class="market">
                <div class="m_top">
                        <span>更多 >></span>
                     </div> 
       
        <div class="m_down">
            <dl v-for="(item,index) in m_kind" :key="index">
                <dt>{{item.title}}</dt>
                <p>{{item.discount}}</p>
                <dd>  <img :src="item.imgUrl" alt=""></dd>
             
            </dl>
  
                
                                     
                                                          

        </div>
    </div>
    </div>
</div>
</template>
<script>
    export default {
        data() {
            return { 
                sales:[
                    require("../assets/img/sale1.png"),
                    require("../assets/img/sale2.png"),
                    require("../assets/img/sale3.png")
                ],
                m_kind:[{
                    title:"手机",
                    discount:"领券享优惠",
                    imgUrl:require('../assets/img/T1LFhgBmx_1RCvBVdK_177_144.webp')
                },{
                    title:"空调",
                    discount:"最高减520",
                    imgUrl:require('../assets/img/T18nLbBgKQ1RCvBVdK_177_144.webp')
                },{
                    title:"冰洗电器",
                    discount:"最高减1000",
                    imgUrl:require('../assets/img/T146bjB4Lv1RCvBVdK_177_144.webp')
                },{
                    title:"电视影音",
                    discount:"满千减百",
                    imgUrl:require('../assets/img/T1AhEgBgE_1RCvBVdK_177_144.jpg')
                },{
                    title:"生活家电",
                    discount:"全场69元起",
                    imgUrl:require('../assets/img/T1WlJgBsh_1RCvBVdK_177_144.webp')
                },{
                    title:"厨房卫浴",
                    discount:"400元劵",
                    imgUrl:require('../assets/img/T1hpAbBXb_1RCvBVdK_177_144.webp')
                },{
                    title:"电脑办公",
                    discount:"领1600元劵",
                    imgUrl:require('../assets/img/T1rnLQBQEv1RCvBVdK_177_144.webp')
                },{
                    title:"智能数码",
                    discount:"拍立得290",
                    imgUrl:require('../assets/img/T1yZKQBXD_1RCvBVdK_177_144.webp')
                },{
                    title:"国美超市",
                    discount:"低至5折",
                    imgUrl:require('../assets/img/T1TO_sBXKT1RCvBVdK_177_144.jpg')
                },{
                    title:"母婴美妆",
                    discount:"低至19.9元",
                    imgUrl:require('../assets/img/T1eQbbBm_T1RCvBVdK_177_144.jpg')
                },{
                    title:"国美智能",
                    discount:"冰箱899元",
                    imgUrl:require('../assets/img/T1SLAgB5E_1RCvBVdK_177_144.webp')
                },{
                    title:"国美家电",
                    discount:"低至9.9元",
                    imgUrl:require('../assets/img/T1kqKgB5bv1RCvBVdK_177_144.webp')
                },]
            }
        }, 
        methods: {
        }
    }
</script>
<style scoped>
.el-carousel__arrow{
    display: none!important;
}

.el-carousel__container {
    position: relative;
    height: 1.235rem!important;
}


    .main_1 {
        height:2.9rem;
        background: #f6f6f6;
        width: 100%;
        overflow: hidden;
    }

    .main_1 .usnew {
        height: 2.90rem;
        /* width: 100%; */
        margin-left: .17rem;
        margin-right: .17rem;
        margin-bottom: .17rem;
        background: white;
        border-radius: .1rem;
    }

    .usnew .u_top {
        height: .43rem;
        width: 100%;
        display: flex;
        background: url('../assets/img/T1X0xsBmKv1RCvBVdK_1065_129.png')no-repeat center;
        background-size: contain;
    }
    .u_top span{
    margin-right: .15rem;
    text-align: right;
    vertical-align: middle;
    width: 100%;
    font-size: .13rem;
    line-height: 0.45rem;
    color: #999;
    }

    .usnew .u_down {
        height: 2.48rem;
        border-top: 0.01rem solid #d9d9ea;
    }

    .u_down ul {
        display: flex;
        justify-content: space-around;
        height: 100%;
        flex-wrap: wrap;

    }

    .u_down ul li {
        width: 50%;
        height: 50%;
        /* border:1px solid #d9d9ea */
    }
    .u_down ul li:nth-child(3){
        width: 30%;
    }
    .u_down ul li:nth-child(4){
        width: 70%;
    }
    .u_down ul li:nth-child(2n) {
        border-bottom: 1px solid #d9d9ea
    }

    .u_down ul li:nth-child(2n+1) {
        border-right: 1px solid #d9d9ea;
        border-bottom: 1px solid #d9d9ea
    }

    .u_down ul li>p {
        margin-bottom: .1rem;
        height: .18rem;
        font-size: .16rem;
        color: black;
        line-height: .19rem;
        padding-left: .1rem;
        display: block;
        width: .8rem;
        float: left;
    }

    .u_down ul li:nth-child(1) p:nth-of-type(1) {
        float: left;
    }
    .u_down ul li:nth-child(3) p{
        width: 100%;
    margin-top: .01rem;
    }
    .u_down ul li:nth-child(3) dl {
        text-align: center;
        font-size: .14rem;;

    }
    .u_down ul li:nth-child(3) dt{
        font-size: .12rem;
        color: #7f6464;
    }
    .u_down ul li:nth-child(3) dd{
    padding-top: .2rem;
    color: #ec7979;
    }
    .u_down ul li .goods {
        display: flex;
        justify-content: space-around;
        width: 100%;
        height: 75%;
        margin-top: .1rem;
    }

    .u_down ul li .goods dl {
        width: 33.3%;
        /* border: .001rem solid red; */
    }

    .u_down ul li .goods dl dt {
        height: 60%;

        /* background: url('../assets/img/settime1.webp')no-repeat center; */
        /* background-size: contain; */
    }

    .u_down ul li .goods dl dt img {
        width: 100%;
    }

    .u_down ul li .goods dl dd {
        /* display: inline-block; */
        line-height: .16rem;
        vertical-align: middle;
        color: #333;
        font-weight: 700;
        font-size: .12rem;
        text-align: center;
    }

    .u_down ul li .goods dl p {
        font-size: .01rem;
        color: #919599;
        text-decoration: line-through;
        text-align: center;
        width: 100%;
    }

    .u_down ul li .m_time {
        border: 1px solid #F20C56;
        border-radius: .04rem;
        width: .5rem;
        height: .12rem;
        margin-left: .02rem;
        display: inline-block;
        line-height: .12rem;
        vertical-align: middle;
        float: left;
        margin-top: .05rem;
        display: flex
    }

    .u_down ul li .m_time p {
        font-size: .12rem;
        padding-top: .04rem;
        margin-top: -.04rem;
        -webkit-transform: scale(0.8);
        color: #d65656;
        text-align: center;
    }

    .u_down ul li span {
    font-size: .12rem;
    color: #fff;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    display: block;
    background: #33c6f8;
    border-radius: .07rem;
    text-align: center;
    width: .6rem;
    margin-top: .03rem;
    }

    .u_down ul li img {
        width: 100%;
        display: block;
    }

    .el-carousel__item h3 {
        color: #475669;
        font-size: .14rem;
        opacity: 0.75;
        line-height: .43rem;
        margin: 0;
    }
 .el-carousel__indicators--vertical {
        right: 0;
        top: 50%;
        -webkit-transform: translateY(-50%);
        transform: translateY(-50%);
        display: none;
    }
    .floor_good{
        height: .93rem;
        background: #f3f3f3
    }
    .floor_good .floor_img{
        height: .93rem;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  
    border-radius: .1rem;
    margin-left: .15rem;
    margin-right: .15rem;
    margin-bottom: .15rem;
    }
    .floor_img ul{
    background: #f3f3f3;
    display: flex;
    }
    .floor_img ul li{
        width: 50%;

    }
    .floor_img ul li:nth-child(1){
        margin-right: .05rem;

    }
    
    .floor_img ul li img{
        width: 100%;
    }
    .main_2 {
        /* height:2.9rem; */
        background: #f6f6f6;
        width: 100%;
        overflow: hidden;
    }

    .main_2 .market {
        /* height: 2.90rem; */
        margin: .17rem;
        background: white;
        border-radius: .1rem;
    }

    .market .m_top {
        height: .43rem;
        width: 100%;
        display: flex;
        background: url('../assets/img/T1RUDbB7L_1RCvBVdK_1065_129.png')no-repeat center;
        background-size: contain;
        margin-top: .3rem;
    }
    .m_top span{
    margin-right: .15rem;
    text-align: right;
    vertical-align: middle;
    width: 100%;
    font-size: .13rem;
    line-height: 0.45rem;
    color: #999;
    }
    .market .m_down{
    height:3.75rem;
    display: flex;
    flex-wrap: wrap;
    }
    .m_down dl{
        width: 25%;
        height: 33.3%;
        border-top: 0.001rem solid #d9d9ea;
        border-left: 0.001rem solid #d9d9ea;
    }
    .m_down dl:nth-child(1),.m_down dl:nth-child(5),.m_down dl:nth-child(9){
        border-left: none;
    }
    .m_down dl dt{
    font-size: .16rem;
    color: #333;
    padding-top: .1rem;
    height: .18rem;
    line-height: .18rem;
    padding-left: 0.1rem;
    }
    .m_down dl p{
    font-size: .12rem;
    color: #666;
    padding-top: .2rem;
    padding-bottom: .07rem;
    height: .14rem;
    line-height: .14rem;
    padding-left: 0.1rem;
    }
    .m_down dl dd{
        border-left: .01rem solid #d9d9ea;
    }
    .m_down dl dd:nth-child(1),.m_down dl dd:nth-child(5),.m_down dl dd:nth-child(9){
        border-left: none;
    }
    .m_down dl dd img{
        display: -webkit-box;
        width: 100%;
        padding-top: .1rem;
    }
</style>