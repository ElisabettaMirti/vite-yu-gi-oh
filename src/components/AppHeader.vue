<script>
// import 

export default {
    data(){
        return{}
    },
    components: {
        
    }
}
</script>

<template>

<header class="d-flex align-items-center">

    <img src="../assets/img/Yu-Gi-Oh-Logo-2001.png" alt="Yu-Gi-Oh! logo" class="ms-2">


<h3>
    Yu-Gi-Oh! API
</h3>
</header>

</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

header{
    height: 120px;

    img{
        height: 100%;
        padding: 2.5rem;
    }
}
</style>