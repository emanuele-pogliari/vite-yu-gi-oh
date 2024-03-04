<script>
import axios from 'axios';
import AppContent from './components/AppContent.vue';
import {store} from './store.js';

export default {
  components: {
    AppContent,
  },
  
  data() {
    return {
      cards: [],

      store,
    }
  },

  created() {
    
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        console.dir(res.data.data)
        this.store.cards = res.data.data
    }).catch(err => {
      console.log(err)
    })

  },
}



</script>

<template>

<AppContent></AppContent>

</template>

<style lang="scss">


</style>
