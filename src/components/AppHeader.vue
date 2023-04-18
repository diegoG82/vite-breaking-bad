<script>
export default {
    name: "AppHeader"
}
</script>

<template>
    <div class="header d-flex ">
        <div class="header-img"><img src="../img/logo.jpg" alt=""></div>

        <h1>Yu-gi-oh API</h1>
    </div>
</template>

<style scoped lang="scss">
.header {
    height: 100px;
    background-color: white;
    justify-content: center;
        // border: 1px solid black;

    img {
        height: 90px;
        line-height: 100px;
        margin-left: 1rem;
        justify-content: center;
    }

    h1 {
        align-items: center;
        line-height: 100px;
        justify-content: center;

    }
}
</style>