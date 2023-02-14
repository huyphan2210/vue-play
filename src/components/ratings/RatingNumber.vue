<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
    numbers: { type: String, required: true }
})

const changeColor = (e: Event) => {
    const element: any = e.currentTarget;
    const elementClass: String = element.getAttribute("class");
    if (elementClass.search('active') >= 0) element.setAttribute("class", "ratingNumber");
    else {
        const ratingNumbers = document.getElementsByClassName("ratingNumber")
        for (let i = 0; i < ratingNumbers.length; i++) {
            ratingNumbers[i].setAttribute("class", "ratingNumber");
        }
        element.setAttribute("class", "ratingNumber active");
    }
}
</script>

<template>
    <div class="ratings">
        <div class="ratingNumber" v-for="num in parseInt(props.numbers)" @click="changeColor">
            {{ num }}
        </div>
    </div>
</template>