<script>
// import 

export default {
    data(){

    },
    components: {
        
    }
}
</script>

<template>

<main>

    <section class="main-content">
        <div class="results-number"></div>
        <div class="cards"></div>
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