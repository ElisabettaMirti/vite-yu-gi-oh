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
    <div class="select-btn">
        <select class="form-select" aria-label="Default select example">
            <option selected>Open this select menu</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
@use '../../node_modules/bootstrap/scss/bootstrap.scss';
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
@use '../styles/general.scss';

div.select-btn{
    width: 250px;
    margin-bottom: 3rem;
    margin-left: 15rem;
}

</style>