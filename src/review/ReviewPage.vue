<script setup>
	import { ref, onMounted } from 'vue';
	import axios from 'axios';
	import ReviewsList from './ReviewList.vue';

	const reviews = ref(null);
	const reviewsUrl = 'https://cwpeng.github.io/live-records-samples/data/reviews.json';
	onMounted(async function() {
		const resp = await axios.get(reviewsUrl);
		const { data } = resp;
		console.log(data);
		reviews.value = data;
	})
</script>

<template>
  <div v-if="reviews === null">資料載入中</div>
  <ReviewsList :reviews="reviews || []" v-else></ReviewsList>
</template>

<style scoped> 
  
</style> 