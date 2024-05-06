<script>

    import CardApp from './CardApp.vue'

    export default {
        data() {
            return {

            }
        },

        components: {
            CardApp,
        }
    }

</script>

<template>
    <div class="container">
        <div class="title">
            <h1>Rick And Morty App</h1>
        </div>
    </div>

    <CardApp />
</template>

<style scoped>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 10vh;
        width: 100%;
        padding: 5%;
    }

    .title {
        font-size: 1.5vw;
    }
</style>