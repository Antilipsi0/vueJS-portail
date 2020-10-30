<template>
  
  <div class="flex">
    <div class="w-1/5">
      <selection-box
        :selection="selection"
      >
      </selection-box>
    </div>
    

    <div class="w-4/5 mt-2">
      <lesson-card 
        v-for="(lesson, index) in team.lessons"
        :key="index"
        :lesson="lesson"
        @add-lesson="addLessonToSelection"
        >
      </lesson-card>
    </div>
    

  </div>
    
</template>

<script>
import teamData from '../data/lessons.json'
import LessonCard from './LessonCard.vue'
import SelectionBox from './SelectionBox.vue'
export default {
  name: "lesson-view",
  components: {
    LessonCard,
    SelectionBox
  },
  data() {
    return {
      team: teamData,
      selection: []
    }
  },
  methods: {
    addLessonToSelection(lesson){
      this.selection.push(lesson)
      this.$emit('child-event', lesson)
    },
    removeLessonToSelection(lesson){
      this.selection.reverse(lesson)
    }
  }
}
</script>

<style>
</style>