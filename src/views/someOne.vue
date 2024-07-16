<template>
  <div class="someOne">
    <van-nav-bar title="七七不菜的游戏" @click-right="onClickRight" border :left-arrow="false">
        <template #right>
            <van-icon name="search" size="18" />
        </template>
    </van-nav-bar>
    
    <van-tabs v-model="activeName">
        <van-tab name="注意事项" title="注意事项">内容 1</van-tab>
        <van-tab name="教程" title="教程">内容 2</van-tab>
        <van-tab name="存档" title="存档">内容 3</van-tab>
        <van-tab name="游戏合集" title="游戏合集">
            <van-tree-select
                :items="items"
                @click-item="clickGame"
                :main-active-index.sync="activeIndex"
                />
        </van-tab>

    </van-tabs>
  </div>
</template>

<script>

import { Button,NavBar,Icon,Tabs,Tab,TreeSelect } from 'vant';
export default {
    components: {
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
            activeName:"注意事项",
            items:[{
                text:"收纳类型类型",
                badge:100,
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
                }]
            },{
                text:"冒险游戏",
                badge:100,
                children:[{
                    text:"很好玩的冒险游戏",
                    id:1
                },{
                    text:"很好玩的冒险游戏2",
                    id:2
                },]
            }]
        }
    },
    methods:{
        // 点击游戏时
        clickGame(data){
            window.open(data.url)
        },
        onClickRight(){
            console.log(111)
        }
    }
};
</script>

<style lang="less">
.someOne{
    .van-nav-bar{
        background: pink;
    }
    .van-sidebar{
        background: #e8e8e8;
    }
}
</style>
