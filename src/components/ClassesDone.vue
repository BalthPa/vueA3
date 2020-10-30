<template>
    <div>{{ClassesData.name}}</div>

    {{ClassesData.name.category}}
aaa
</template>

<script>

import ClassesData from '../assets/data/classes.json'

export default {
    name:"classes-done",
    data(){
        return {
            ClassesData: ClassesData
        }
    }
} 
</script>

<style>

</style>