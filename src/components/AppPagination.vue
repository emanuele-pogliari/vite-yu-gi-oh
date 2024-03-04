<script>

import {store} from '../store.js';

export default {
    name: 'AppPagination',

    data() {
        return {
            store,
        }
    }
}
</script>


<template>
    <div class="pagination">
        Found {{ store.cards.length }} cards
    </div>
</template>


<style lang="scss">

.pagination{

    margin-bottom: 20px;
    padding: 30px;

    border-radius: 20px;
    background-color: #212529;
    color: white;
    font-size: 18px;
    font-weight: 700;
}

</style>