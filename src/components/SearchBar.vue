<script>

import { store } from '../store';

export default {
    name: "SearchBar",
    emits: ["filter"],
    data() {


        return {
            store,
            // typeofarch: ["Alien"]
        }

    },


};

</script>

<template>
    <div class="text-center">
    <select class="select-type p-2 m-4 " v-model="store.selectedType" @change="$emit('filter')">
        <option value="">All</option>
        <option value="Alien">Alien</option>
        <option value="Ally of justice">Ally of Justice</option>
        <option value="Ancient Gear">Ancient Gear</option>

    </select>
</div>
</template>
<style scoped lang="scss">
.select-type {
    background-color: white;
   }
</style>