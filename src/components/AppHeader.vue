<script>
export default {
    name: "AppHeader"
}</script>

<template>
<div class="header d-flex">
    <div class="header-img"><img src="../img/logo.jpg" alt=""></div>
    
    <h1>Yu-gi-oh API</h1>
</div>
</template>

<style scoped lang="scss">

.header{
    height: 100px;
    border : 1px solid black;
    background-color: white;
    .header-img{
        height: 100px;
        img{
            height: 80px;
        }
    }
    
}


</style>