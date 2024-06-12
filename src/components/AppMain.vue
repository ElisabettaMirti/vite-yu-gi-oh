<script>
import axios from 'axios';

export default {
    data(){
        return{
            CardsList: []
        }
    },
    components: {
        
    },
    methods: {
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(function (response) {
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

<main>

    <section class="main-content">
        <div class="results-number"></div>
        <div class="cards p-4"></div>
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
    }
}

div.results-number{
    height: 100px;
    background-color: #212529;
}


</style>