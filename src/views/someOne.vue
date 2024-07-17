<template>
    <div class="someOne">
      <van-nav-bar title="七七不菜的游戏" border :left-arrow="false">
      </van-nav-bar>
      
      <van-tabs v-model="activeName">
          <van-tab name="教程" title="教程">
            <tutorialVue />
          </van-tab>
          <van-tab name="存档" title="存档">
            <div style="padding: 0 10px;">
              <div class="item">
                  <p class="title">
                      <span class="icon"></span>
                      <span>IOS</span>
                  </p>
                  <p class="index">1.点击进入游戏后，点击右上角，使用safasi浏览器打开</p>
                  <p class="index">2.点击浏览器下方中间箭头按钮，下拉找到添加到主屏幕即可</p>
                  <p class="index">3.从桌面打开游戏即可存档</p>
              </div>
              <div class="item">
                  <p class="title">
                      <span class="icon"></span>
                      <span>安卓</span>
                  </p>
                  <p class="index">1.点击进入游戏后，点击右上角，使用浏览器打开</p>
                  <p class="index">2.点击添加到书签</p>
                  <p class="index">3.从书签打开即可存档</p>
              </div>
            </div>
          </van-tab>
          <van-tab name="游戏合集" title="游戏合集">
              <van-tree-select
              height="100%"
                  :items="items"
                  @click-nav="clickNav"
                  @click-item="clickGame"
                  :main-active-index.sync="activeIndex"
                  />
          </van-tab>
      </van-tabs>
    </div>
  </template>
  
  <script>
  import { Button,NavBar,Icon,Tabs,Tab,TreeSelect } from 'vant';
  import tutorialVue from './tutorial.vue';
  
  export default {
      components: {
        tutorialVue,
          [Button.name]: Button,
          [NavBar.name]: NavBar,
          [Icon.name]: Icon,
          [Tabs.name]: Tabs,
          [Tab.name]: Tab,
          [TreeSelect.name]: TreeSelect,
      },
      data() {
          return{
              activeIndex:0,
              activeName:"教程",
              items:[{
                  text:"收纳类型类型",
                  badge:15,
                  children:[{
                      text:"收纳物语",
                      url:"https://cdn.hanyougame.cn/snwy_web_1.0.1/web-mobile/index.html",
                      id:1
                  },{
                      text:"收纳达人",
                      url:"https://webgame-6gzwg8ti52e46012-1310209978.tcloudbaseapp.com/109/1.0.0/web-mobile/index.html",
                      id:2
                  },{
                      text:"小小收纳",
                      url:"https://z10.tanyu.mobi/tanpaixyx/18002/web/1.0.170/index.html",
                      id:3
                  },{
                      text:"收纳天才",
                      url:"https://updatecdn.chutaonet.cn/collect/web_game/web-mobile/index.html",
                      id:4
                  },{
                      text:"我的收纳摊",
                      url:"https://z10.tanyu.mobi/tanpaixyx/16003/web/1.0.110/index.html",
                      id:5
                  },{
                      text:"脑洞人爱收纳",
                      url:"https://maoyumeng.cdn.xiaojing.work/chdl/cydmx/web/web-mobile1/index.html",
                      id:6
                  },{
                      text:"喵星人爱收纳",
                      url:"https://maoyumeng.cdn.xiaojing.work/chdl/mxrasn/remote/web/web-mobile/index.html",
                      id:7
                  },{
                      text:"超级收纳馆",
                      url:"https://changshazhise01-1254961065.cos.ap-guangzhou.myqcloud.com/zhise/cjjyg/web/index.html",
                      id:8
                  },{
                      text:"第亿次收纳",
                      url:"https://maoyumeng.club/dycsn/web/web-mobile/index.html",
                      id:9
                  },{
                      text:"鸭鸭收纳大师",
                      url:"https://www.rewanyouxi.com/games/snds/",
                      id:10
                  },{
                      text:"收纳模拟器",
                      url:"http://112.74.33.201:8080/cnmnq",
                      id:11
                  },{
                      text:"沉浸解压馆",
                      url:"https://cooperation.pailedi.com/web2/gameClean/web-mobile23/index.html",
                      id:12
                  },{
                      text:"樱花校园收纳",
                      url:"https://game.k54k.cn/gamefile/ttd68da03049b2f17c02/web-mobile/",
                      id:13
                  },{
                      text:"鼠鼠收纳",
                      url:"https://trident.icu/web-mobile/index.html",
                      id:14
                  },{
                      text:"收纳人生",
                      url:"https://www.lekonghd.cn/newsndrs/3.1.6/",
                      id:15
                  }]
              },{
                  text:"烹饪游戏",
                  badge:5,
                  children:[{
                      text:"旅行餐车",
                      url:"https://qcdn.bdoggame.com/ttgame/lvxingcc/webVer/index.html",
                      id:1
                  },{
                      text:"开了个西餐厅",
                      url:"https://game.csquyou.com/mhxcd/",
                      id:2
                  },{
                      text:"夜市餐厅",
                      url:"https://game2.sfplay.net/nightMarket/v1",
                      id:3
                  },{
                      text:"武林大厨",
                      url:"https://file.gugudang.com/res/down/public/p_myhotel/web-mobile/lts/index.html",
                      id:4
                  },{
                      text:"喵喵小厨娘",
                      url:"https://enjoygaga-1300513096.cos.ap-shanghai.myqcloud.com/game/cooking/index.html",
                      id:5
                  }]
              }]
          }
      },
      methods:{
          // 点击游戏时
          clickGame(data){
              window.open(data.url)
          },
          clickNav(index){
            if(index == 2){
              this.$router.push("/search")
            }
          }
      }
  };
  </script>
  
  <style lang="less">
  .someOne{
      .van-nav-bar{
          background: #ee0a24;
      }
      .van-sidebar{
          background: #e8e8e8;
      }
      .item{
          margin-top: 10px;
          box-shadow: 0 0 8px #00000048;
          padding: 10px;
          .title{
              margin: 0;
              display: flex;
              align-items: center;
              font-weight: 800;
              .icon{
                  display: inline-block;
                  width: 5px;
                  height: 25px;
                  background: pink;
                  margin-right: 10px;
              }
          }
          .index{
              text-align: left;
              font-size: 14px;
              margin: 8px 0 8px 14px;
          }
      }
  }
  
  </style>
  