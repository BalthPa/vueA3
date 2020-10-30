<template>
   <div class="rounded overflow-hidden shadow-lg" :class="whichCategory">
        <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{{classe.name}}</div>
            <p class="text-white text-base">{{classe.description}}</p>
        </div>
        <div class="px-6 pt-4 pb-2">
          <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">{{classe.category}}</span>
          <span class="inline-block rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2" :class="isDone">
              <classes-button :text="classe.done"></classes-button>
          </span>
        </div>

  </div>
</template>

<script>

export default {
    name: "classes-card",
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

      isDone(){
          if (this.classe.done == "Complété"){
              return "bg-green-300"
          }
            return "bg-red-300"
      }
    }
}
</script>

<style>

</style>