<script>
import AppNav from "./AppNav.vue";
import CardItem from "./CardItem.vue";
import AppPagination from "./AppPagination.vue";

import { store } from "../store.js";

export default {
    name: 'AppContent',

    components:  {
        AppNav,
        CardItem,
        AppPagination,
    },

    data() {
        return {
            store,
        }
    },
}

</script>

<template>
<AppNav></AppNav>

<div class="content">
    
    <div class="select-container">
        <select name="archetype" id="">
            <option value="alien">Alien</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
        </select>
    </div>
    
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
    width:75%;
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
    width: 75%;
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