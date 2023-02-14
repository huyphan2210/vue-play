<script setup lang="ts">
import RatingNumber from '../ratings/RatingNumber.vue';
</script>

<template>
   <div class="starIcon">
      <img src="../../img/icon-star.svg" alt="Star Icon">
    </div>
    <h1 id="ratingQuestion">How did we do?</h1>
    <p id="ratingQuote">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>
    <RatingNumber numbers="5"/>
    <button type="button">SUBMIT</button>
</template>

<style scoped>

</style>
