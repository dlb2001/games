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
                  badge:3,
                  children:[{
                      text:"收纳物语",
                      url:"https://cdn.hanyougame.cn/snwy_web_1.0.1/web-mobile/index.html",
                      id:1
                  },{
                      text:"隐秘的档案",
                      url:"https://file-hidfile.kidikidi.net/secretfiles/h5/promote/after/web-mobile/index.html",
                      id:7
                  },{
                      text:"超级收纳馆",
                      url:"https://changshazhise01-1254961065.cos.ap-guangzhou.myqcloud.com/zhise/cjjyg/web/index.html",
                      id:8
                  }]
              },{
                  text:"烹饪游戏",
                  badge:2,
                  children:[{
                      text:"旅行餐车",
                      url:"https://qcdn.bdoggame.com/ttgame/lvxingcc/webVer/index.html",
                      id:1
                  },{
                      text:"夜市餐厅",
                      url:"https://game2.sfplay.net/nightMarket/v1",
                      id:3
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
  