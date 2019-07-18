<template>
    <!-- <div class="item"> -->
        <router-link :to="linkTo">
            <strong>{{otitle}}</strong>
        </router-link>
    <!-- </div> -->
</template>
<script>
export default {
    props:{
        otitle:String,
        linkTo:String
    },
    data(){
        return{}
    }
}
</script>
<style scoped>
strong{
    font-weight: 400;
    font-size: .26rem;
    line-height:.26rem ;
}
a{
    text-decoration: none;
    color: black;
}
</style>
