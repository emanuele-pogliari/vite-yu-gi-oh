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
       <p class="title-card">{{ card.name }}</p>
        <p class="archetype">{{ card.archetype }}</p>
    </li>
</template>

<style lang="scss">

@use '../styles/variables' as *;

.card{
    display: flex;
    flex-flow: column;
    gap: .7em;

    width: calc(100% / 5 - $cardsGap / 5 * 4);
    text-transform: uppercase;
    background-color: #D48F38;

    border-radius:10px;
    overflow-y: hidden;

    .title-card{
        color: white;
    }

    .archetype{
        padding: 10px 0;
        font-size: 0.9em;
    }
}

</style>