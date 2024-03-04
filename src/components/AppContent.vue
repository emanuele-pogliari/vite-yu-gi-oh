<script>
import AppNav from "./AppNav.vue";
import CardItem from "./CardItem.vue";

export default {
    name: 'AppContent',

    components:  {
        AppNav,
        CardItem,
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
    <CardItem></CardItem>
</div>

</template>

<style lang="scss">
.content{
  background-color: orange;
  select{
    display: block;
  }
}
</style>