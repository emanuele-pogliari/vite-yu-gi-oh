<script>
    export default {
        name: 'AppLoader',
    }
</script>
<template>
    <div class="loader-container">
        <div class="loader-box">
            <div class="loader"></div>
            <p class="loader-text">LOADING...</p>
        </div>
    </div>
</template>
<style>
    .loader-container{
        width: 100vw;
        height: 100vh;
    }
    .loader {
        width: 230px;
        height: 40px;
        border-radius: 40px;
        color: #514b82;
        border: 2px solid;
        position: relative;
        overflow: hidden;
        margin-bottom: 10px;
    }

    .loader-box{
        top:50%;
        left:50%;
        position: absolute;
        transform: translate(-50%);
        text-align: center;
    }

    .loader-text{
        font-size: 1.4em ;
    }

    .loader::before {
        content: "";
        position: absolute;
        margin: 2px;
        width: 14px;
        top: 0;
        bottom: 0;
        left: -20px;
        border-radius: inherit;
        background: currentColor;
        box-shadow: -10px 0 12px 3px currentColor;
        clip-path: polygon(0 5%, 100% 0, 100% 100%, 0 95%, -30px 50%);
        animation: l14 1s infinite linear;
    }

    @keyframes l14 {
        100% {
            left: calc(100% + 20px)
        }
    }
</style>