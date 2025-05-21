<script setup>
  import { onMounted, ref } from 'vue';
  import axios from 'axios';
  import ProductsList from './ProductsList.vue';

  const products = ref(null);
  const productsUrl = 'https://cwpeng.github.io/live-records-samples/data/products.json';
  onMounted(async function() {
    const resp = await axios.get(productsUrl);
    const { data } = resp;
    console.log(data);
    products.value = data;
  });
</script>

<template> 
  <div v-if="products === null">資料載入中</div>
  <ProductsList :products="products || []" v-else></ProductsList>
</template>

<style scoped> 
  
</style> 