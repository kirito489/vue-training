<script setup>
  import NavComp from './Nav.vue';
  import MainComp from './Main.vue'
  import { ref } from 'vue';

  const text = ref('主要的網站內容');
  const change = function() {
    text.value = '新的網站內容'
  };
</script>

<template> 
  <NavComp title='這是網站標題'></NavComp>
  <MainComp
  color = 'white'
  bgc = 'blue'>
  </MainComp>
</template>

<style scoped> 
  
</style>
