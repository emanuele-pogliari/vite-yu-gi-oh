<script>

import { store } from "../store.js";

export default {
    name: 'AppSelect',

    data() {
        return {
            store,
        }
    }
}


</script>


<template>
<div class="select-container">
    <select name="archetype" id="" @click="$emit('search')">
        <option :value= "archetype.archetype_name" v-for="archetype in store.archetype">{{ archetype.archetype_name }}</option>
    </select>
</div>
</template>


<style>

</style>

