<script>
import AppCard from './AppCard.vue';
import AppLoader from './AppLoader.vue';

import { store } from "../store"


export default {
    name: "AppMain",

    components: {
        AppCard,
        AppLoader

    },

    data() {
        return {
            store
        }
    },

}
</script>

<template>
    <main>
        <select class="select-type p-2 m-4" aria-label="Default select example">
                <option selected>Choose!</option>
                <option value="Alien">Alien</option>
                <option value="Noble Knight">Noble Knight</option>
                <option value="Melodious">Melodious</option>
                <option value="Archfiend">Archfiend</option>
            </select>

        <div class="container p-4">
            
            <div class="card-container p-4 ">
                <h6 class="found text-white">TROVATE 39 CARDS</h6>
                <AppLoader v-if="store.loading" />
                <div class="row row-cols-5 ">
                    <div class="col mt-2 mb-2 " v-for="card in store.cards">
                        <AppCard :card="card" />
                    </div>
                </div>

            </div>


        </div>
    </main>
</template>

<style scoped lang="scss">
main {
    background-color: rgb(212, 143, 56);
}
.select-type{
    background-color: white;
}

.container {
    background-color: white;
    width: 80%;


    .card-container {
        background-color: white;
    }

    .found {
        width: 100%;
        height: 80px;
        background-color: black;
        line-height: 80px
    }

}
</style>