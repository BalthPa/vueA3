<template>
    <div class="rounded overflow-hidden shadow-lg" :class="whichCategory">
        <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{{classe.name}}</div>
            <p class="text-white text-base">{{classe.description}}</p>
        </div>
        <div class="px-6 pt-4 pb-2">
          <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">{{classe.category}}</span>
          <span class="inline-block rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2" :class="whichDifficulty">{{classe.difficulty}}</span>
          <button @click="DeleteClasses" class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">Supprimer</button>
        </div>

  </div>
</template>

<script>

export default {
    name: "done-cards",
    props: ['classe'],
    computed: {
      whichCategory(){
        if(this.classe.category == "Dev"){
            return "bg-orange-500"
        }
        else if (this.classe.category == "Créa"){
            return "bg-red-500"
        }
        else if (this.classe.category == "3D"){
            return "bg-green-500"
        }
          return "bg-yellow-500"
      },
      whichDifficulty(){
          if(this.classe.difficulty == "Facile"){
              return "bg-green-600"
          }
          else if(this.classe.difficulty == "Moyen"){
              return "bg-orange-600"
          }
          return "bg-red-700"
      },
      isDone(){
          if (this.classe.done == "Complété"){
              return "bg-green-300"
          }
            return "bg-red-300"
      }
    },
    methods:{
        DeleteClasses(classe){
            this.$emit('delete-classes', classe)
        }
    }
}
</script>

<style>

</style>