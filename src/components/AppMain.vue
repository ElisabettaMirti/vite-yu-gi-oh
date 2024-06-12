<script>
import axios from 'axios';
import SingleCard from './SingleCard.vue'

export default {
    data(){
        return{
            CardsList: []
        }
    },
    components: {
        SingleCard
    },
    methods: {
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then( (response) => {
            // handle success
            console.log(response.data.data);
            this.CardsList = response.data.data;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
        .finally(function () {
            // always executed
        });
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>

<main class="container-fluid p-5">

            <section class="main-content container p-5">
                <div class="results-number d-flex align-items-center">
                    <h4 class="ms-4">
                        Found {{ CardsList.length }} cards
                    </h4>
                </div>
                
                <div class="cards-list">
                    <div class="cards p-2" v-for="(card, index) in CardsList" :key="index">
                        <div class="card">
                            <img class="card-img-top" :src="card.card_images[0].image_url" :alt="card.name">
                            <div class="card-body">
                                <h5 class="card-title fw-bold">
                                    {{ card.name }}
                                </h5>
                                <p class="card-text">
                                    {{ card.archetype }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>                
            </section>

    
</main>

</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

main{
    background-color: #d48f38;

    section.main-content{
        background-color: white;
        width: 90%;
    }
}

div.results-number{
    height: 100px;
    background-color: #212529;
    color: white;
}

div.cards-list{
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
}

div.cards{
    width: calc((100%/5) - .5rem);
    align-self: flex-start;
    border-color: transparent;
    text-align: center;

    div.card-body {
        background-color: #d48f38;
        
        h5{
            color: white;
        }
    }
}

</style>