<template>
  <div class="bg-orange-500 p-2 text-center text-white text-xl">
    <a href="#" @click="changeComponent('lesson-view')">Tous les cours</a> | 
    <a href="#" @click="changeComponent('selection-list')">Mes cours</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>
</style>