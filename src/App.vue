<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import SearchBar from './components/SearchBar.vue'
import axios from "axios";
import { store } from "./store"


export default {
  components: {
    AppHeader,
    AppMain,
    AppLoader,
    SearchBar,
    emits: ["filter"],
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    // store.loading = true;
    // axios.get(store.apiURL).then((resp) => {
    //   this.store.cards = resp.data.data;
    //   store.loading = false;
    // })
    this.getArchetype();

  },
  methods: {
    getArchetype() {
      this.store.loading = true;
      const params = {}
      if (this.store.selectedType) {
        params.status = this.store.selectedType;
      }
      axios.get(this.store.apiURL, {
        params:{
          archetype:"alien"
        }
      }).then(resp => {
        this.store.cards = resp.data.data;
      }).catch(error => {
        console.log(error);
      }).finally(() => {
        this.store.loading = false;
      })
    },

    handlefilter() {
      this.getArchetype();
      console.log("ciao");
    }
  },
}




</script>

<template>
  <AppHeader />

  <SearchBar @filter="handlefilter" />


  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>