<template>
    <a :href="Tolink"><p>{{kind}}</p></a>
</template>
<script>
export default {
    props:{
        kind:String,
        Tolink:String
    }
}
</script>
<style scoped>
.box{
    /* margin: 10px; */
    /* display: flex; */
    width: 100%;
}
a{
    width: 25%;
    float: left;
    margin-bottom: 10px; 
}
p{
    width: 1.5rem;
    height: .7rem;
    font-size: .28rem;
    background-color: #f5f5f5;
    text-align: center;
    line-height: .6rem;
    border-radius: 20px;

}
</style>
