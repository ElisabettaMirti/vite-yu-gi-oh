<script>
// import 

export default {
    data(){
        return{

        }
    },
    components: {
        
    },
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
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
</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

div.card-body {
        background-color: #d48f38;
        
        h5{
            color: white;
        }
    }
</style>
