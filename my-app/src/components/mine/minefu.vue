<template>
    <div class="demo">
        <Mineitem v-for="(v,i) in arr" :key="i" :oimg="v.img" :otitle="v.title"></Mineitem>
    </div>
</template>
<script>
import Mineitem from './mineitem'
export default {
    components:{
        Mineitem
    },
    data(){
        return{
            arr:[]
        }
    },
    created() {
        this.axios({
            url:"/link/data",
            method:"get"
        }).then((ok)=>{
            // console.log(ok.data.myaccount);
            this.arr=ok.data.myaccount
        })
    },
}
</script>
<style scoped>
.demo{
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}
</style>
