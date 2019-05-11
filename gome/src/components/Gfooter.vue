<template>
    <div>
       
        <ul >
            <li v-for="(item,idx) in navs" :key="idx" :class="{active:idx===active}"><i :class="item.icon" @click="tab(idx)"></i>
                <p>{{item.title}}</p>
            </li>
           
        </ul>
     
    </div>
</template>

<script>
    export default {
        data(){
            return {
                navs:[{
        icon:"el-icon-s-home icfon",
        title:"首页",
        path:"gome"
   },{
        icon:"el-icon-menu icfon",
        title:"分类",
        path:"kind"
   },{
        icon:"el-icon-sunset icfon",
        title:"优选",
        path:"youxuan"
   },{
        icon:"el-icon-shopping-cart-full icfon",
        title:"购物车",
        path:"cart"
   },{
        icon:"el-icon-s-custom icfon",
        title:"我的",
        path:"my"
   }],
   active:0
            }
        },
        methods:{
            tab(idx){
                this.active=idx
                if(idx==0){
                    this.$router.push('home')
                }else if(idx==1){
                    this.$router.push('kind')
                }else if(idx==2){
                    this.$router.push('youxuan')
                }else if(idx==3){
                    this.$router.push('cart')
                }else if(idx==4){
                    this.$router.push('my')
                }

                }
            }
        }
   

</script>
<style scoped>
    div {
        position: fixed;
        bottom: 0;
        left: 0;
        height: .47rem;
        /* line-height: 1rem; */
        width: 100%;
        background: #f2f2f2;
        color: black;
        font-size: .12rem;
    }
    div ul{
        display: flex;
        justify-content: space-around;
        /* line-height:.2rem; */
    }
    .icfon{
        text-align: center;
        /* padding-top: .05rem; */
        font-size: .3rem;
    }
    div ul li{
        display: flex;
        flex-direction: column;
       
    }
    div ul li p{
        text-align: center;
    }
    .active{
         color: #ff648c;
    }
</style>