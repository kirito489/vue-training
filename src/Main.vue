<script setup>
  import { onMounted, onUpdated, onUnmounted, ref } from 'vue';

  const counter = ref(0);
  let scheduleId;
  onMounted(function() {
    console.log('組件掛載完成');
    scheduleId = window.setInterval(function() {
      console.log('每隔1秒鐘，數字的加1');
      counter.value = counter.value + 1;
    }, 1000);
  });
  onUpdated(function() {
    console.log('組件更新完成');
  });
  onUnmounted(function() {
    console.log('組件卸載完成');
    window.clearInterval(scheduleId);
  });

  const text = ref('主要的網站內容');
  const changeText = function() {
    text.value = text.value === '新的網站內容' ? '主要的網站內容' : '新的網站內容'
  };
</script>

<template> 
  <main>
    <div> {{ counter }} </div>
    <div> {{ text }} </div>
    <button @click="changeText">改變文字內容</button>
  </main>
</template>

<style scoped> 
  main {
    padding: 10px;
    background-color: aqua;
  }

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
