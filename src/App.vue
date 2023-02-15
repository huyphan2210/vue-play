<script setup lang="ts">
import { ref } from 'vue'
import Ratings from './components/body/Ratings.vue';
import ThankYou from './components/body/ThankYou.vue';

const MAX_RATING = 5;

const rating = ref(0);

const handleSubmit = (ratingNumber: string) => {
  rating.value = parseInt(ratingNumber);
}

</script>

<template>
  <Ratings :max-rating="MAX_RATING" v-if="rating === 0" @submit="handleSubmit"/>
  <ThankYou v-else :max-rating="MAX_RATING" :rating="rating"/>
</template>

<style scoped>
</style>
