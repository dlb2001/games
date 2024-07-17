<template>
    <div class="search">
      <van-nav-bar :placeholder="true" @click-left="$router.push('/allGames')" fixed title="七七不菜的游戏" border left-arrow   left-text="返回" />
        <van-search
            v-model="searchName"
            show-action
            placeholder="请输入游戏名称"
            @search="search"
            >
            <template #action>
                <van-button @click="search" size="small" type="primary">搜索</van-button>
            </template>
        </van-search>
        <van-list
        finished-text="没有更多了"
        >
            <p class="item" @click="openGame(item.url)" v-for="(item,index) in data" :key="index">
                <span style="width: 60px;display: inline-block">{{ index+1 }}</span>
                <span>{{ item.name }}</span>
                <span></span>
            </p>
        </van-list>
    </div>
</template>

<script>
import dataList from "./games.js";
import { NavBar, Icon,Field,Button,List,Notify,Search    } from "vant";

export default {
  components: {
    [NavBar.name]: NavBar,
    [Icon.name]: Icon,
    [Field.name]: Field,
    [Button.name]: Button,
    [List.name]: List,
    [Notify.name]: Notify,
    [Search.name]: Search,
  },
  data() {
    return {
        searchName:"",
        data:[]
    };
  },

  mounted() {
    this.data = dataList
  },
  methods: {
    openGame(url){
        window.open(url)
    },
    search(){
        if(this.searchName == ""){
            this.data = dataList
        }
        let a = this.searchName; //用户输入的字符串
        let str = ['',...a,''].join('.*'); //转化成正则格式的字符串
        let reg = new RegExp(str) //正则
        let list = []
        for(var i=0;i<dataList.length;i++){
            if(reg.test(dataList[i].name)){
                list.push(dataList[i])
            }
        }
        this.data = list
    }
  },
};
</script>

<style lang="less">
.search {
  .van-nav-bar {
    background: #ee0a24;
  }

  .item{
    border-bottom: 1px solid #e8e8e8;
    padding: 10px 10px;
    display: flex;
    align-items: center;
    margin: 0;
  }
}

</style>