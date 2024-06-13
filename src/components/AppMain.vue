<script>
import axios from 'axios';
import MainCardsList from './MainCardsList.vue';
import AppLoader from './AppLoader.vue';
import MainSelect from './MainSelect.vue';
import {store} from '../store.js'

export default {
    data(){
        return{
            store,
            isLoaded: false
        }
    },
    components: {
        MainCardsList,
        AppLoader,
        MainSelect
    },
    methods: {
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype='  + store.archetypeSelected )
            .then( (response) => {
                // handle success
                console.log(response.data);
                this.store.cards = response.data;
                // this.isLoaded = true;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });
        },

        loadInOneSec(){
            setTimeout(() => {
                this.isLoaded = true;
            }, 1000);
        },

        
    },
    created(){
        this.getCards();
        this.loadInOneSec();
    }
}
</script>

<template>

<main class="container-fluid p-5">
    <MainSelect @searched="getCards()" />
    <MainCardsList v-if="isLoaded"/> 
    <AppLoader v-else />
</main>

</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';



main{
    background-color: #d48f38;
    position: relative;

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


</style>