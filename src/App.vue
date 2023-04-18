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
      const params = {
        num: 20,
        offset: 0
      }
      if (this.store.selectedType) {
        params.archetype = this.store.selectedType;
      }
      axios.get(this.store.apiURL, {
        params
        
        
      }).then(resp => {
        this.store.cards = resp.data;
      }).catch(error => {
        console.log(error);
      }).finally(() => {
        this.store.loading = false;
      })
    },

    handlefilter() {
      console.log("ciao");
      this.getArchetype();
      
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