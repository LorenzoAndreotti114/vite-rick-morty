<script>
    import axios from 'axios';

    export default {
        data() {
            return {
                cardsData: []
            }
        },
        created() {
            axios
                .get("https://rickandmortyapi.com/api/character")
                .then((resp) => {
                    console.log(resp);
                    this.cardsData = resp.data.results
                    console.log(this.cardsData);
                })
        }
    }


</script>

<template>
    <div class="card-container">

        <div class="card" v-for="(CardCreator, index) in cardsData">
            <div class="card-image">
                <img :src="cardsData[index].image" alt="">
            </div>

            <div class="card-title f-size">
                <div class="card-name">
                    <h2>
                        {{ cardsData[index].name }}
                    </h2>
                </div>

                <div>
                    {{ cardsData[index].status }}
                </div>

                <div>
                    {{ cardsData[index].species }}
                </div>

            </div>
        </div>

    </div>
</template>

<style scoped>

    img {
        border-radius: 50%;
    }

    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .card-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        width: 100%;
        padding: 5%;
    }

    .card-image {
        height: 20vw;
        width: 20vw;
        margin: 10% 0;
    }

    .card-title {
        width: 100%;
        display: flex;
        flex-direction: column;
        text-align: center;
    }

    .card-name {
        font-size: 1.2vw;
        width: 100%;
    }
</style>