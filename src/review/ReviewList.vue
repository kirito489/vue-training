<script setup>
  defineProps(['reviews']);
</script>

<template> 
  <div class="list">
    <div class="review" v-for="review in reviews">
      <div class="name"> {{ review.name }} </div>
      <div class="message"> {{ review.message }} </div>
      <div class="star">星星: {{ review.star }} </div>
    </div>
  </div>
</template>

<style scoped> 
  .list {
    line-height: 1.5rem;
  }

  .review {
    padding: 15px 0;
    border-bottom: 1px solid black;
  }
  
  .review .name {
    font-weight: bold;
  }
</style> 