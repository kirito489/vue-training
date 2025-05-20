<script setup>
  import NavComp from './Nav.vue';
  import MainComp from './Main.vue'
  import { ref } from 'vue';

  const subtitle = ref('這是網站的副標題');
  const subsubtitle = ref('這是網站的副副標題')
  const updateSubtitle = function() {
    subtitle.value = '這是網站新的副標題';
  };
  const updateSubSubtitle = function() {
    subsubtitle.value = '這是網站新的副副標題'
  }
</script>

<template> 
  <NavComp 
  title = '這是網站標題'
  :subtitle = 'subtitle'
  :subsubtitle = 'subsubtitle'
  ></NavComp>
  
  <MainComp
    color = 'white'
    bgc = 'blue'
    @update = 'updateSubtitle'
    @update-1 = 'updateSubSubtitle'
  ></MainComp>
</template>

<style scoped> 
  
</style>
