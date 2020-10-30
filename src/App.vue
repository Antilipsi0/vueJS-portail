<template>

  <nav-bar
    @change-component="changeSelectedComponent"
  >
  </nav-bar>
  
  <keep-alive include="lesson-view">
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @child-event="selectionUpdate"
    >
    </component>
  </keep-alive>
  
  
</template>

<script>
import LessonView from './components/LessonView.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    LessonView,
    SelectionList,
    NavBar
  },
  data() {
    return {
      selectedComponent: 'lesson-view',
      lessonSelection: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list"){
        return { selection: this.lessonSelection }
      }
      return false
    },
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.lessonSelection.push(value)
    },
  }
}
</script>

<style>

</style>
