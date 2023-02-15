<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
    numbers: { type: String, required: true }
})

const submitIsActive = ref(false);
const emits = defineEmits(['rating', 'submitIsActive'])
const changeColor = (e: Event) => {
    const element: any = e.currentTarget;
    const elementClass: String = element.getAttribute("class");
    if (elementClass.search('active') >= 0) {
        element.setAttribute("class", "ratingNumber");
        emits('rating', 0);
        submitIsActive.value = false;
    } else {
        const ratingNumbers = document.getElementsByClassName("ratingNumber")
        for (let i = 0; i < ratingNumbers.length; i++) {
            ratingNumbers[i].setAttribute("class", "ratingNumber");
        }
        element.setAttribute("class", "ratingNumber active");
        emits('rating', element.innerText);
        submitIsActive.value = true;
    }
    emits('submitIsActive', submitIsActive.value);
}
</script>

<template>
    <div class="ratings">
        <div class="ratingNumber" v-for="num in parseInt(props.numbers)" @click="changeColor">
            {{ num }}
        </div>
    </div>
</template>