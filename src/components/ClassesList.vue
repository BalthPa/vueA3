<template>
    <h1 class="text-3xl text-center">{{classesData.name}}</h1>
    <div class="flex flex-wrap justify-center">
        <classes-card v-for="(classe, index) in classesData.classes" :key="index" :classe="classe" class="w-1/4 m-5"></classes-card>
    </div>
</template>

<script>

import classesData from '../assets/data/classes.json'
import ClassesCard from './ClassesCard'

export default {
    name:"classes-list",
    components: {
        ClassesCard
    },
    data() {
        return {
           classesData : classesData, 
        }
    },
}
</script>

<style>

</style>