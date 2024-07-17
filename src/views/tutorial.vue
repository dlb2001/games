<template>
  <div class="tutorial">
    <div class="item">
        <p class="title">
            <span class="icon"></span>
            <span>提示</span>
        </p>
        <p class="index">1.某些游戏无法打开可能由于官方修复，可先玩其他游戏</p>
        <p class="index">2.本网站游戏正持续更新，请保存好此链接</p>
        <p class="index">3.所有游戏均为去广破解版，无需担心广告问题</p>
        <p class="index">4.所有游戏安卓、IOS、平板通用</p>
        <p class="index">5.破解版游戏可能弹出安全提示，链接绝对安全，请放心食用</p>
    </div>
    <div class="item">
        <p class="title">
            <span class="icon"></span>
            <span>教程</span>
        </p>
        <p class="index">1.导航栏-游戏合集可查看游戏大致分类，点击游戏名称即可跳转游玩</p>
        <p class="index">2.搜索：点击右上角搜索按钮即可跳转至搜索页面进行搜索</p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="less">
.tutorial{
    padding: 0 10px;
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