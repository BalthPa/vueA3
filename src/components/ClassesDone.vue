<template>
    <h1 v-if="classesDoneArray.length == 0" class="text-3xl text-center">Aucun cours sélectionnés</h1>

    <h1 v-else-if="classesDoneArray.length == 1" class="text-3xl text-center">Cours sélectionné : {{classesDoneArray.length}}</h1>

    <h1 v-else class="text-3xl text-center">Cours sélectionné : {{classesDoneArray.length}}</h1>

    <div class="flex flex-wrap justify-center">
        <done-cards v-for="(classe,index) in classesDoneArray" :key="index" :classe = classe class="w-1/4 m-5" @delete-classes ="deleteClasses"></done-cards>
    </div>

</template>

<script>

import ClassesData from '../assets/data/classes.json'
import DoneCards from './DoneCards'

export default {
    name:"classes-done",
    data(){
        return {
            ClassesData: ClassesData
        }
    },
    components: {
        DoneCards
    },
    props: ['classesDoneArray'],
    methods:{
        deleteClasses(classe){
            console.log("Caca")
            this.$emit('delete-classe', classe)
        }
    },
    computed: {
        
    }
} 
</script>

<style>

</style>