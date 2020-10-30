<template>
  <div 
    class="border m-2 p-2 flex justify-between text-white"
  >
    <div>
      <h1 class="text-lg text-white font-bold">{{ lesson.name }}</h1>
      <h2> Intervenant : {{ lessonProfUp }} </h2>
      <p>Date : {{ lesson.date }}</p>
      <p>Description : {{ lesson.description }}</p>
      <p>Nombres d'heures : {{ lesson.hour }}</p>
    </div>
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "lesson-card",
  props: ['lesson'],
  data(){
    return {
      lessons: []
    }
  },
  computed: {
    lessonProfUp(){
      return this.lesson.prof.toUpperCase()
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-lesson', this.lesson)
    }
  }
}
</script>

<style scoped>
</style>