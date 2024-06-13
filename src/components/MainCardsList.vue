<script>
import SingleCard from './SingleCard.vue';

export default {
    data(){
        return{
            
        }
    },
    components: {
        SingleCard
    },
    props: {
        cards: {
            type: Array,
            required: true
        }
    },
}
</script>

<template>
<section class="main-content container p-5">
        <div class="results-number d-flex align-items-center">
            <h4 class="ms-4">
                Found {{ cards.length }} cards
            </h4>
        </div>
    <div class="cards-list">
        <SingleCard class="cards p-2" v-for="(card, index) in cards" :key="index" :card="card"/>
    </div>
</section>

</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

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
}

</style>