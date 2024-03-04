<script>

export default {
    name: 'CardItem',

    props: {
        card: Object,
    },
}

</script>

<template>

    <li class="card">
        <img :src="card.card_images[0].image_url_small" :alt="card.name">
        {{ card.name }}
    </li>
</template>

<style lang="scss">

@use '../styles/variables' as *;

.card{
    display: flex;
    flex-flow: column;
    gap: .7em;

    width: calc(100% / 5 - $cardsGap / 5 * 4);
    color: white;
    text-transform: uppercase;
}

</style>