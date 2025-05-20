<script setup>
  import { ref } from 'vue';
  import MainComp from './Main.vue';

  const visible = ref(true);
  const hide = function() {
    visible.value = false;
  };
  const show = function() {
    visible.value = true;
  };
</script>

<template> 
  <MainComp v-if="visible"></MainComp>
  <button @click="hide">隱藏</button>
  <button @click="show">重新顯示</button>
</template>

<style scoped> 
  button {
    border: 1px solid black;
    background-color: aliceblue;
    color: black;
  }

  button:hover {
    opacity: 0.7;
  }

  button:active {
    opacity: 0.5;
  }
</style>
