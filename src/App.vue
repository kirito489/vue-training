<script setup>
  import { ref } from 'vue';
  import ProductsPage from './product/ProductsPage.vue';
  import ReviewsPage from './review/ReviewPage.vue';

  const page = ref('product')
  const change = function(clickedPage) {
    page.value = clickedPage
  }
</script>

<template>
  <nav>
    <span :class="page === 'product' ? 'current' : ''" @click="change('product')">產品資料</span>
    <span :class="page === 'review' ? 'current' : ''" @click="change('review')">評論訊息</span>
  </nav>
  <main>
    <ProductsPage v-if="page === 'product'"></ProductsPage>
    <ReviewsPage v-if="page === 'review'"></ReviewsPage>
  </main>
</template>

<style scoped> 
  nav {
    font-size: 20px;
  }

  nav span {
    margin-right: 10px;
  }

  nav span.current {
    font-weight: bold;
  }
</style> 