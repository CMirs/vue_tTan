<template>
    <div>
        <header>
            <ul>
                <li></li>
                <li><i></i><input type="text" disabled value="55英寸4K电视低至1899元" /></li>
                <li @click="cart"></li>
                <li @click="login">登录</li>
            </ul>
        </header>
    </div>

</template>
<script>
    export default {
        methods:{
            cart(){
                this.$router.push('cart')
            },
            login(){
                this.$router.push('login')
            }
        }
    }

</script>
<style scoped>
    div{
        /* position: fixed;
        top: 0;
        left: 0 */
    }
    header {
        height: .44rem;
        display: flex;
    }

    header ul {
        display: flex;
        justify-content: space-around;
        flex: 1
    }

    header ul li:nth-child(1) {
        flex: 1;
        background: url(../assets/img/grass_logo.png)no-repeat center;
        background-size: .3rem;
    }

    header ul li:nth-child(2) {
        display: flex;
        flex: 4;
        flex-direction: column;
        justify-content: center;
        position: relative;
    }

    header ul li:nth-child(2) i {
        background: url(../assets/img/search_icon.png)no-repeat center;
        position: absolute;
        left: .02rem;
        height: .17rem;
        width: 0.17rem;
        background-size: .17rem;
    }

    header ul li:nth-child(2) input {
        height: .3rem;
        width: 100%;
        border-radius: .1rem;
        border: none;
        background: #f6f6f6;
        color: #999;
        padding-left: .2rem;

    }

    header ul li:nth-child(3) {
        flex: 1;
        background: url(../assets/img/grass_cart.png)no-repeat center;
        background-size: .25rem;
        margin-left: .1rem;
    }

    header ul li:nth-child(4) {
        flex: 1;
        font-size: .14rem;
        line-height: .44rem;
    }
</style>