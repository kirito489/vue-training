<script setup>
  import { onMounted, ref } from 'vue';
  import axios from 'axios';
  import List from './List.vue';

  const products = ref(null);
  const url = 'https://cwpeng.github.io/live-records-samples/data/products.json';
  onMounted(async function() {
    const resp = await axios.get(url);
    console.log(resp);
    const { data } = resp;
    console.log(data);
    products.value = data;
  });
</script>

<template> 
  <div class="headline">產品資料列表</div>
  <div v-if="products === null">資料載入中</div>
  <List :products="products || []" v-else></List>
</template>

<style scoped> 
.headline {
  font-size: 20px;
  font-weight: bold;
}
</style> 