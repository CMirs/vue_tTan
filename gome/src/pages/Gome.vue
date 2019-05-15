<template>
  <div>
    <router-view></router-view>
    <Gheader />
    <Lunbo />
    <div class="g_nav">
      <div class="g_nav_t">
        <ul v-for="(item,index) in kinds" :key='index'  v-show="active ==index" class="g_nav1">
          <!-- {{item}} -->
          <li v-for="(items,idx) in item"  :key='idx' >
            <img :src="items.imgs">
            <p>{{items.title}}</p>
          </li>
        </ul>
      </div>
      <ul class="g_nav_d">
        <!-- <li v-for="(item,idx) in kinds" :key="idx" :class="{active:idx===active}" @click="tt(idx)" /> -->
        <li v-for="(item,idx) in kinds" :key="idx" :class="active==idx?'active':''" @click="tt(idx)" />
      </ul>
      </div>
      <News/>
    <Guild/>
   <Srt/>
   
      <Top/>
      <Gfooter />
  </div>
</template>

<script>
  import Gfooter from '../components/Gfooter.vue';
  import Gheader from '../components/Gheader.vue';
  import Lunbo from '../components/lunbo.vue';
  import News from '../components/news.vue';
  import Guild from '../components/Guild.vue';
  import Top from '../components/reTop.vue';
  import Srt from '../components/Script.vue';
  export default {
    components: {
      Gfooter,
      Gheader,
      Lunbo,
      News,
      Guild,
      Srt,
      Top
    },
    data() {
      return {
        kinds: [
            [{
              imgs: require('../assets/img/T1MXWsBghv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1tu_bBTxv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1u_A_B4bv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1uZDsByhv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1yuC_B5h_1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T11gZvBChQ1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T12V_jBQDv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T18pxjBmD_1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T10eDbBmVT1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T10eDbBmVT1RCvBVdK_195_129.png'),
              title: "排行榜"
            }],
            [{
              imgs: require('../assets/img/T10eDbBmVT1RCvBVdK_195_129.png'),
              title: "排行榜1"
            },
            {
              imgs: require('../assets/img/T1aJWbBm__1RCvBVdK_195_129.png'),
              title: "排行榜1"
            },
            {
              imgs: require('../assets/img/T1cEZsBgJT1RCvBVdK_195_129.png'),
              title: "排行榜1"
            },
            {
              imgs: require('../assets/img/T1BZd_BgD_1RCvBVdK_195_129.png'),
              title: "排行榜1"
            },
            {
              imgs: require('../assets/img/T1eQhgBjWv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1FO_bBQWT1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1Ii_bBmbb1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1J9_vBgxb1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T1K0__BTYv1RCvBVdK_195_129.png'),
              title: "排行榜"
            },
            {
              imgs: require('../assets/img/T10eDbBmVT1RCvBVdK_195_129.png'),
              title: "排行榜"
            }]
       ],
      active: 0
      }
    },
    methods: {
      tt(idx) {
        this.active = idx;
        // console.log(kinds.left);

      }
    }
  }
</script>
<style scoped>
  .g_nav {
    height: 1.71rem;

    display: flex;
    font-size: .12rem;
    padding-top: .1rem;
    box-sizing: border-box;
    flex-direction: column;

  }

  .g_nav .g_nav_t {
    height: 1.65rem;

  }

  .g_nav_t .g_nav1 {
    display: flex;

    flex-wrap: wrap;
    justify-content: space-around;
    text-align: center;
  }

  .g_nav1 li {}

  .g_nav1 li img {
    width: .65rem;
    height: .43rem;
  }

  .g_nav .g_nav_d {
    height: .6rem;
    width: 100%;

    display: flex;
    justify-content: center;
    padding-top: .08rem;
  }

  .g_nav_d li {
    height: .1rem;
    background: #e0dbdb;
    width: .1rem;
    border-radius: .1rem;
    padding-top: .01rem;
    margin-left: .05rem;
    text-indent: -99999px;
  }

  .active {
    background: #f20c59 !important;
  }
</style>