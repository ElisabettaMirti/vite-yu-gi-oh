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
        
    }
}
</script>

<template>
<span class="loader"></span>
</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

.loader {
    margin-top: 10rem;
    width: 100%;
    height: 12px;
    display: inline-block;
    background-color: #FFF;
    background-image: linear-gradient(45deg, rgba(0, 0, 0, 0.25) 25%, transparent 25%, transparent 50%, rgba(0, 0, 0, 0.25) 50%, rgba(0, 0, 0, 0.25) 75%, transparent 75%, transparent);
    font-size: 30px;
    background-size: 1em 1em;
    box-sizing: border-box;
    animation: barStripe 1s linear infinite;
}

@keyframes barStripe {
    0% {
    background-position: 1em 0;
    }
    100% {
    background-position: 0 0;
    }
}

</style>
