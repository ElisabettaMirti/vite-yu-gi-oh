<script>
// import 

export default {
    data(){
        return{}
    },
    components: {
        
    },
    props: {
        archetypes: {
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <div class="select-btn">
        <select class="form-select">
            <option selected>Choose an archetype</option>
            <option v-for="(archetype , index) in archetypes":key="index" value="index" @click="$emit('searched')">
                {{ archetype.archetype_name }}
            </option>
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