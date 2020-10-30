<template>
  <div class="container w-4/5 text-center text-white mx-auto mt-4">
    <h1 class="text-lg font-bold text-white">Mes cours</h1>

    <div v-if="selection.length == 0">
      <p>Aucun cours sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="lesson in selection"
        :key="lesson.name" 
        class="border my-4 p-2 text-white"
      >
        <h3>{{ lesson.name }} ({{ lesson.date }})</h3>
        <span>Commence à {{ lesson.time }} jusqu'à {{ lesson.time2 }}</span>
        <p>{{ lesson.description }}</p>
        <img :src="require('../assets/img/' + lesson.photo)" alt="">
        
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
}

</script>

<style>
</style>