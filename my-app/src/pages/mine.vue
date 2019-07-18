<template>
    <div>
        <div class="head">
            <router-link to="/#"><i class="el-icon-setting c_icon"></i></router-link>
            <router-link to="/#"><i class="iconfont icon-kefu c_icon"></i></router-link>
        </div>
        <div class="top">
            <div @scroll="scrollEvent">
                <Minefu></Minefu>
            </div>
            <My></My>
            <div class="activity">
                <Mine_activity v-for="(v,i) in arrActivity" :key="i" :oimg="v.img" :title="v.title" :describe="v.describe"></Mine_activity>
            </div>
            <div class="tool">
                <div class="tool_top">
                    <h3>常用工具</h3>
                </div>
                <Tool></Tool>
            </div>
            <p>——猜你喜欢
                <span>.EXPLORE——</span>
            </p>
            <Tool></Tool>
        </div>
        
    </div>
</template>
<script>
import Minefu from '../components/mine/minefu'
import My from '../components/order/my'
import Mine_activity from '../components/mine_activity/mine_activity'
import Tool from '../components/tool/tool'
export default {
     components:{
         Minefu,
         My,
         Mine_activity,
         Tool
     },
      data(){
        return{
            arrActivity:[]
        }
    },
    created() {
        this.axios({
            url:"/link/data",
            method:"get"
        }).then((ok)=>{
            // console.log(ok.data.mine_activity);
            this.arrActivity=ok.data.mine_activity
        })
    },
    methods: {
        scrollEvent(e){
            console.log(e)
        }
    },
}
</script>
<style scoped>
.head{
    position: fixed;
    left: 0;
    width: 100%;
    height: 1.8rem;
    background-color: #09bffe;
    display: flex;
    justify-content:space-between;
    z-index: 9;
}
.c_icon{
    font-size: .62rem;
    margin: 10px;
    color: #ffffff;
}
.top{
    padding-top: 2.05rem;
    background-color: #eeeeee;
    /* height: 1.24rem; */
    overflow: hidden;
}
.activity{
     background-color: white;
     height: 1.5rem;
     margin: 10px 0;
}
.tool{
    width: 100%;
    height: 4.57rem;
    background-color: white;
}
.tool_top{
    padding: 10px; 
    border-bottom:1px solid #ededed;
}
h3{
    font-size: .32rem;
}
P{
    height: .6rem;
    font-size: .26rem;
    color: #b4b4b4;
    text-align: center;
    line-height: .6rem;
}
span{
    color: #a6c1d4;
}
</style>
