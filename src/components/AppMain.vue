<script>
import axios from 'axios';
import MainCardsList from './MainCardsList.vue';
import AppLoader from './AppLoader.vue';
import MainSelect from './MainSelect.vue';

export default {
    data(){
        return{
            cards: [],
            archetypes: [],
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
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=100')
            .then( (response) => {
                // handle success
                console.log(response.data.data);
                this.cards = response.data.data;
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
            }, 6000);
        },

        getArchetype(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then( (response) =>{
                console.log(response.data);
                this.archetypes = response.data;
            })
            .catch(function (error) {
                console.log(error);
            })
        }
    },
    created(){
        this.getCards();
        this.loadInOneSec();
        this.getArchetype();
    }
}
</script>

<template>

<main class="container-fluid p-5">
    <MainSelect :archetypes="archetypes" @searched="" />
    <MainCardsList :cards="cards" v-if="isLoaded"/> 
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