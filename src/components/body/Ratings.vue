<script setup lang="ts">
import { ref } from 'vue';
import RatingNumber from '../ratings/RatingNumber.vue';

const ratingNumber = ref(0);

const props = defineProps({
   maxRating: { type: Number, required: true}
})
const emits = defineEmits(['submit'])

const handleRating = (rating: string) => {
   ratingNumber.value = parseInt(rating);
}

const checkSubmit = (isActive: boolean) => {
   const submitButton = document.getElementsByTagName('button')[0];
   if (isActive) {
      submitButton.setAttribute('class', 'activeSubmit')
   } else {
      submitButton.setAttribute('class', '')
   }
}

const submitRating = () => {
   if (ratingNumber.value !== 0) {
      emits('submit', ratingNumber.value);
   }
}

</script>

<template>
   <div class="starIcon">
      <img src="../../img/icon-star.svg" alt="Star Icon">
    </div>
    <h1 id="ratingQuestion">How did we do?</h1>
    <p id="ratingQuote">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>
    <RatingNumber :numbers="String(props.maxRating)" @rating="handleRating" @submit-is-active="checkSubmit"/>
    <button type="button" @click="submitRating">SUBMIT</button>
</template>

<style scoped>

</style>
