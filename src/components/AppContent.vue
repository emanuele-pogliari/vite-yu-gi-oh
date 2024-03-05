<script>
import AppNav from "./AppNav.vue";
import CardItem from "./CardItem.vue";
import AppPagination from "./AppPagination.vue";
import AppSelect from "./AppSelect.vue";

import axios from 'axios';


import { store } from "../store.js";

export default {
    name: 'AppContent',

    components:  {
        AppNav,
        CardItem,
        AppPagination,
        AppSelect,
        
    },

    data() {
        return {
            store,
        }
    },

    methods:{
    filter() {
        if(this.store.archeSearch == 0){
          axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
          .then(res => {
          this.store.cards = res.data.data;
        });
        } else{
          axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=" + this.store.archeSearch)
        .then(res => {
        this.store.cards = res.data.data;
        });
        }
      },
  },

}

</script>

<template>
<AppNav></AppNav>

<div class="content">
    
  <AppSelect @search="filter()"></AppSelect>
    
    <div class="inner-container">
        <AppPagination></AppPagination>
        
        <ul>
        <CardItem v-for="currentCard in store.cards"
                :card="currentCard"></CardItem>
        </ul>
    </div>
</div>

</template>

<style lang="scss">
@use '../styles/variables' as *;
.content{
  background-color: #2e95d0;
  padding-top: 35px;

  .select-container{
    width:85%;
    margin: 0 auto;
    padding-left: 20px;
  }

  select{
    display: block;
    margin-bottom: 35px;
    padding: 12px;
    border-radius: 5px;
    border:1px solid white;
    background-color: white;
    width: 200px;

  }

  .inner-container{
    width: 85%;
    margin: 0 auto;

    padding: 70px;
    border-radius: 20px;
    
  }
  
  ul {
    list-style-type: none;

    display: flex;
    flex-wrap: wrap;
    
    gap: $cardsGap;

    text-align: center;
}

}
</style>