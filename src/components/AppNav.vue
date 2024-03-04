<script>

export default {
    name: 'AppNav',
}

</script>

<template>
    <nav class="nav">
        <img src="/public/img/yu-gi-oh.png" alt="">
        <div class="title">Yu-Gi-Oh-Api</div>
    </nav>
</template>

<style lang="scss">
.nav{
    display: flex;
    gap:25px;
    align-items: center;

    width: 100%;
    height: 105px;
    
padding-left: 40px;

    background-color: white;

    img{
        width: 75px;
        height: 100%;
    }

    .title{
      font-size: 42px;  
    }



}

</style>