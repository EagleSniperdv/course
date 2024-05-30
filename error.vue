<template>
    <NuxtLayout name="404">
    <div class="wrapper">
        <div class="text-4xl">This page is not found, boss</div>
        <button class="font-bold button" @click="goBack"> Go Back</button>
    </div>
    </NuxtLayout>
</template>

<script>
export default {
    methods: {
        goBack() {
        this.$router.push('/')
        }
    }
    }
</script>

<style scoped>
    .wrapper{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 50vh;
        width: 50vw;
        margin-top: 50px;
        border-radius: 50%;
        background: yellow;
    }
.button {
    padding: 4px 6px;
    margin: 10px 0px;
    background: red;
    color: white;
    border: none;
    border-radius: 10px;
}
</style>