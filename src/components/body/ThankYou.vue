<script setup lang="ts">

const props = defineProps({
    maxRating: { type: Number, required: true },
    rating: { type: Number, required: true }
})

</script>

<template>
    <div class="thankYou">
        <div class="thankYouImg">
            <img src="../../img/illustration-thank-you.svg" alt="Thank You Img">
        </div>
        <div class="ratingResult">
            You selected {{ rating }} out of {{ maxRating }}
        </div>
        <div class="thankYouSentence">
            <h1>Thank you!</h1>
            <p>
                We appreciate you taking the time to give a rating. If you ever need more support, 
                don't hesitate to get in touch!
            </p>
        </div>
    </div>
</template>

<style scoped>
.thankYou {
    display: flex;
    flex-direction: column;
    align-items: center;
}

    .ratingResult {
        margin-top: 1.5em;
        color: hsl(25, 97%, 53%);
        background-color: hsl(213, 19%, 18%);
        padding: 0.5em;
        border-radius: 1em;
    }
    .thankYouImg {
        width: 100%;
        display: flex;
        justify-content: center;

    }
    .thankYouSentence {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

        .thankYouSentence h1 {
            color: white;
        }

        .thankYouSentence p {
            margin-top: 0;
            color: hsl(216, 12%, 54%);
        }

</style>