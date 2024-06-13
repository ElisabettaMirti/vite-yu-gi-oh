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

<div class="cards-list">
    <SingleCard class="cards p-2" v-for="(card, index) in cards" :key="index" :card="card"/>
</div>                

    


</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';


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