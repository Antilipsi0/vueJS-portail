<template>
  <div class="border bg-orange-500 text-white text-center m-4 p-4">
    Nombre de cours : {{ selection.length }}
    <span v-if="dateSelection">cours ajouté</span>
    <span v-else>cours ajoutés</span>
    <br>
    <ul>
      <li v-for="lesson in selection" :key="lesson.name">{{ lesson.name }}</li>
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
    hourSelection(){
      if(this.selection.length < 2){
        return true
      }
      return false
    }
  }
}
</script>

<style>
</style>