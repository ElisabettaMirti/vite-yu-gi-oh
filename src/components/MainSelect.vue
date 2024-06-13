<script>
import {store} from '../store.js';
import axios from 'axios';

export default {
    data(){
        return{
            store
        }
    },
    components: {
        
    },
    methods: {
        getArchetype(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then( (response) =>{
                console.log(response.data);
                this.store.archetypes = response.data;
            })
            .catch(function (error) {
                console.log(error);
            })
        },
        newSearch(archetype){
                store.archetypeSelected = archetype;
            }
    },
    created(){
        this.getArchetype();
    }
}
</script>

<template>
    <div class="select-btn">
        <select class="form-select">
            <option selected>Choose an archetype</option>
            <option v-for="(archetype , index) in store.archetypes" :key="index" :value="archetype.archetype_name" @click="newSearch(archetype.archetype_name), $emit('searched')">
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