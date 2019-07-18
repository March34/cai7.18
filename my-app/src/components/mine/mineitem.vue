<template>
    <div class="box">
        <div class="left">
            <img :src="oimg" alt="">
            <p>用户名：{{otitle}}</p>
        </div>
        <div class="right">
            <i class="iconfont icon-saoyisao"></i>
            <i class="iconfont icon-ico"></i>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        oimg:String,
        otitle:String,
    }
}
</script>
<style scoped>
.box{
    width: 90%;
    height: 1.1rem;
    background-color: white;
    position: absolute;
    top: -27px;
    border-bottom: 10px solid #10c6ff;
    border-radius:5px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}
.right{
    margin: 0 10px 20px 0;
}
img{
    float:left;
    width: 1.2rem;
    border-radius: 50%;
    /* background-color: aqua; */
}
p{
    float:left;
    font-size: .26rem; 
    color:#c9c9c9;
    margin-top: 15px;
}
</style>
