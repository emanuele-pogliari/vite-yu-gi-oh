<script>
import AppNav from "./AppNav.vue";
import CardItem from "./CardItem.vue";

import { store } from "../store.js";

export default {
    name: 'AppContent',

    components:  {
        AppNav,
        CardItem,
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
    <select name="archetype" id="">
        <option value="alien">Alien</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
    </select>
    <ul>
        <CardItem v-for="currentCard in store.cards"
                :card="currentCard"></CardItem>
    </ul>
    
</div>

</template>

<style lang="scss">
@use '../styles/variables' as *;
.content{
  background-color: orange;
  select{
    display: block;
  }
  ul {
    list-style-type: none;

    display: flex;
    flex-flow: row wrap;
    
    gap: $cardsGap;
}
}
</style>