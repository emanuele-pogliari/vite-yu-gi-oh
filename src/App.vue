<script>
import axios from 'axios';
import AppContent from './components/AppContent.vue';
import AppLoader from './components/AppLoader.vue';
import {store} from './store.js';

export default {
  components: {
    AppContent,
    AppLoader,
  },
  
  data() {
    return {

      store,
      isLoading: true,
      select:"Alien",
    }
  },

  created() {
    
    axios
      .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${this.select}&num=20&offset=0`)    
      .then(res => {
        console.dir(res.data.data)
        this.store.cards = res.data.data
        this.isLoading = false;
    }).catch(err => {
      console.log(err)
    })

  },
}

</script>

<template>

<AppLoader v-if="isLoading == true"></AppLoader>

<AppContent></AppContent>

</template>

<style lang="scss">





</style>
