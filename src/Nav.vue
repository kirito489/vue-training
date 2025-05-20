<script setup>
  defineProps(['title'])
</script>

<template> 
  <nav> {{ title }} </nav>
</template>

<style scoped> 
  nav {
    padding: 10px;
  }
</style>
