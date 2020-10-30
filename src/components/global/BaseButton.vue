<template>
  <button class="btn-orange">
    {{ text }}
  </button>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style scoped>
.btn-orange {
  @apply bg-orange-500 text-white font-bold py-2 px-4 rounded;
}
.btn-orange:hover {
  @apply bg-orange-700;
}
</style>