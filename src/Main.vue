<script setup>
  import { ref } from 'vue';

  const text = ref('主要的網站內容');
  const change = function() {
    text.value = '新的網站內容'
  };
</script>

<template> 
  <main>
    <div @click="change"> {{ text }} </div>
  </main>
</template>

<style scoped> 
  main {
    padding: 10px;
    background-color: aquamarine;
  }
</style>
