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
    <select name="archetype" id="">
        <option></option>
    </select>
</div>
</template>


<style>

</style>

