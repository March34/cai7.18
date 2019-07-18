<template>
    <div class="box">
        <h3>盒马鲜生西安兰岛店 实时热搜</h3>
        <div class="xia">
            <Slistitem v-for="(v,i) in arrSearch1" :key="i" :kind="v.kind"></Slistitem>
        </div>
        <h3>新品•时令</h3>
        <div class="xia">
            <Slistitem v-for="(v,i) in arrSearch2" :key="i" :kind="v.okind"></Slistitem>
        </div>
    </div>
</template>
<script>
import Slistitem from './slistitem'
export default {
    components:{
        Slistitem
    },
    data(){
        return{
            arrSearch1:[],
            arrSearch2:[],
        }
    },
    created() {
        this.axios({
            url:"/link/data",
            method:"get"
        }).then((ok)=>{
            // console.log(ok.data.my_search1);
            this.arrSearch1=ok.data.my_search1
            this.arrSearch2=ok.data.my_search2
        })
    }
}
</script>
<style scoped>
.box{
    margin: 10px;
    
}
.xia{
    overflow: hidden;
    height:1.7rem;
    margin-top: 20px;
}
h3{
    font-size: .4rem;
    margin-top: .28rem;
}
</style>
