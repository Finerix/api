<template>
    <h1 class="main-title">Get your daily dose of CATBOYS</h1>
    <div class="box">
        <div>
            <img :src="images.url" alt="Catboy image" class="thumb">
        </div>
        <div>
            <button class="btn" onClick="window.location.reload();">NEXT</button>
        </div>
    </div>
</template>

<script setup>
    //fetch the images
    const{ data: images } = await useFetch('https://api.catboys.com/img')
    defineProps(['images'])
</script>

<style scoped>
    .main-title{
        text-align: center;
    }
    .thumb{
        max-width: 50%;
        max-height: 50%;
        border: solid 1px black;
    }
    .box{
        text-align: center;
        display: flex;
        justify-content: center;
        flex-direction: column;
    }
    .btn{
        max-width: 300px;
        max-height: 100px;
        padding: 1em;
        text-align: center;
        background-color: aquamarine;
        font-size: 32px;
        color: black;
        border: 0px;
        border-radius: 10%;
    }
</style>