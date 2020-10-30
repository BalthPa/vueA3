<template>
  <div class="bg-blue-500 p-2 flex justify-around">  
    
    <a v-for="(link, index) in navigation" :key="index" @click="selectComponent(link.component)" href="#" class="text-xl">
        {{link.name}}
    </a>

  </div>
</template>

<script>
export default {
    name: 'nav-bar',
    data(){
        return {
            navigation: [
                {name: "Tous les cours", component: "classes-list"},
                {name: "Cours fait", component: "classes-done"}
            ]
        }
    },
    methods: {
        selectComponent(comp){
            this.$emit('nav', comp)
        }
    }
}
</script>

<style>

</style>