<template>
    <div class="main_1">
        <div class="usnew">
            <div class="u_top">
                <span></span>
                <el-carousel height=".43rem" direction="vertical" :autoplay="true" class="t_right">
                    <el-carousel-item v-for="(item,idx) in news" :key="idx">
                        <h3 class="medium">{{ item.title }}</h3>
                    </el-carousel-item>
                </el-carousel>
            </div>
            <div class="u_down">
                <ul>
                    <li>
                        <p>国秒美杀</p>
                        <div class="m_time">
                            <p>{{hour_1}}:</p>
                            <p>{{minute_1}}:</p>
                            <p>{{sec_1}}</p>
                        </div>
                        <div class="goods">
                            <dl>
                                <dt><img src="../assets/img/settime1.webp" alt=""></dt>
                                <dd>￥ 9</dd>
                                <p>￥29</p>
                            </dl>
                            <dl>
                                <dt><img src="../assets/img/settime1.webp" alt=""></dt>
                                <dd>￥ 9</dd>
                                <p>￥29</p>
                            </dl>
                            <dl>
                                <dt><img src="../assets/img/settime1.webp" alt=""></dt>
                                <dd>￥ 9</dd>
                                <p>￥29</p>
                            </dl>
                        </div>
                    </li>
                    <li>
                        <p style="color:#48a6ff">新品抢先</p><span>联想小新清新版</span><img
                            src="../assets/img/T1HgJ_BmW_1RCvBVdK_355_144.jpg" alt="">
                    </li>
                    <li>
                        <p style="color:#fd851d">值得买</p><span>大家都在买</span><img
                            src="../assets/img/T1btL_BsZv1RCvBVdK_355_144.jpg" alt="">
                    </li>
                    <li>
                        <p style="color:#fd851d">品牌热卖</p><span>西门子牌之日 每满千减百</span><img
                            src="../assets/img/T1gmdbBvLv1RCvBVdK_355_144.jpg" alt="">
                    </li>
                </ul>
            </div>

        </div>
    </div>

</template>
<script>




    export default {
        data() {
            return {
                news: [{
                    title: "智能音箱89元起"
                }, {
                    title: "整点购迷你加湿器"
                }, {
                    title: "投资金条 优惠购金"
                }],
                // 时间初始状态
                hour_1: '--',
                minute_1: '--',
                sec_1: '--'
            }
        }, created() {
            this.time();
        },
        methods: {
            time() {
                let stopTime = new Date(2019, 5, 15, 12, 12, 12);
                var Timer = setInterval(function () {
                    var nowTime = new Date();
                    var shicha = (stopTime - nowTime) / 1000;


                    this.hour_1 = Math.floor((shicha / 60 / 60) % 24);
                    this.minute_1 = Math.floor((shicha / 60) % 60);
                    this.sec_1 = Math.floor(shicha % 60);
                    if (this.hour_1 == 0 && this.minute_1 == 0 && this.sec_1 == 0) {
                        //关闭定时器
                        clearInterval(Timer);
                    }
                    // console.log(555);

                }.bind(this), 1000);
            },



        }
    }
</script>
<style scoped>
    .main_1 {
        height: 3.24rem;
        background: #f6f6f6;
        width: 100%;
        overflow: hidden;
    }

    .main_1 .usnew {
        height: 2.90rem;
        /* width: 100%; */
        margin: .17rem;
        background: white;
       border-radius: .1rem;
    }

    .usnew .u_top {
        height: .43rem;
        width: 100%;
        display: flex;

    }

    .u_top span {
        display: inline-block;
        width: 25%;
        background: url('../assets/img/T1yEhbB7J_1RCvBVdK_120_28.png')no-repeat center;
        background-size: contain;
        margin: 0 0.05rem;
    }

    .u_top .t_right {
        width: 70%;
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
    }

    .u_down ul li:nth-child(1) p:nth-of-type(1) {
        float: left;
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
        color: #666;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        padding-left: .1rem;
        display: block;
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

    /* .el-carousel__item:nth-child(2n) {
        background-color: #99a9bf;
    }

    .el-carousel__item:nth-child(2n+1) {
        background-color: #d3dce6;
    } */

    .el-carousel__indicators--vertical {
        right: 0;
        top: 50%;
        -webkit-transform: translateY(-50%);
        transform: translateY(-50%);
        display: none;
    }
</style>