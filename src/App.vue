<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import axios from "axios";
import { store } from "./store"


export default{
  components: {
    AppHeader,
    AppMain,
    AppLoader
  },
  data() {
    return {
      store
    }
  },
  mounted(){
    store.loading = true;
    axios.get(store.apiURL).then((resp) => {
      this.store.cards = resp.data;
      store.loading = false;
    })

  //   axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
  // .then((resp) => {
  //     const myData = resp.data.data;
  //   })

  }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>