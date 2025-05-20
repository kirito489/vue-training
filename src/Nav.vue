<script setup>
  defineProps(['title', 'subtitle', 'subsubtitle'])
</script>

<template> 
  <nav>
    <div> {{ title }} </div>
    <div> {{ subtitle }} </div>
    <div> {{ subsubtitle }} </div>
  </nav>
</template>

<style scoped> 
  nav {
    padding: 10px;
  }
</style>
