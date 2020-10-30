<template>
  <div class="border bg-orange-500 text-white text-center m-4 p-4">
    Nombre de cours : {{ selection.length }}
    <span v-if="dateSelection">cours ajouté</span>
    <span v-else>cours ajoutés</span>
    <br>
    <ul>
      <li v-for="lesson in selection" :key="lesson.name">{{ lesson.name }}   
    </li>  
       <button class="border rounded bg-orange-600 m-2 p-2" v-on:click="removeElement(lesson)">Supprimer</button>
    </ul>

  </div>
  
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],
  computed: {
    dateSelection(){
      if(this.selection.length < 2){
        return true
      }
      return false
    },
    methods: {
      removeElement: function (lesson) {
      this.lessons.splice(lesson);
    }
    }
  },
}
</script>

<style>
</style>