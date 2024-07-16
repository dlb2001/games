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
