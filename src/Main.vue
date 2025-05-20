<script setup>
  import { ref } from 'vue';

  const text = ref('主要的網站內容');
  const change = function() {
    text.value = '新的網站內容'
  };
  defineProps(['color', 'bgc']);
  const emit = defineEmits(['update', 'update-1'])
  const updateParentSubSubtitle = function() {
    emit('update-1');
  };
</script>

<template> 
  <main :style="{ color, backgroundColor: bgc  }">
    <div @click="change"> {{ text }} </div>
    <button @click="$emit('update')">改變副標題</button>
    <button @click="updateParentSubSubtitle">改變副副標題</button>
  </main>
</template>

<style scoped> 
  main {
    padding: 10px;
  }

  button {
    border: 1px solid black;
    background-color: aliceblue;
    color: black;
  }
</style>
