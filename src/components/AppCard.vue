<script>
export default {
    name: "AppCard",
    props: {
        card: Object,
    },
};

</script>


<template>
    <div class="card text-center ">
        <img :src="card.card_images[0].image_url_small" alt="" srcset="">
        <h4 class="text-white">{{ card.name }}</h4>
        <p>{{ card.archetype }}</p>
        <!-- <p>{{ card.card_prices[0].ebay_price }}</p> -->

    </div>
</template>


<style scoped lang="scss">
.card {
    background-color: rgb(212, 143, 56);
    // border: 1px solid black;

    height: 450px;
    h4 {
        text-transform: uppercase;
        // color: white;
    }
}
</style>