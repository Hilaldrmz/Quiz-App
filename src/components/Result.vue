<script setup>
import { RouterLink } from "vue-router";

const { quizQuestionLength, numberOfCorrectAnswers } = defineProps(["quizQuestionLength", "numberOfCorrectAnswers"]);

</script>

<template>
    <div class="results">
        <p>Your Results...</p>
        <h1>
            {{ numberOfCorrectAnswers }} / {{ quizQuestionLength }}
        </h1>
    </div>
    <div class="home-router-div">
        <RouterLink to="/" class="home-router"> Go Back </RouterLink>
    </div>
</template>

<style lang="scss" scoped>
.results {
    text-align: center;
    padding: 100px 0;

    p {
        font-size: 25px;
    }

    h1 {
        font-size: 80px;
    }
}
.home-router-div {
    display: flex;
    justify-content: center;
    .home-router {
        border: none;
        background-color: $secondary-color;
        margin: 0;
        border-radius: 15px;
        padding: 10px;
        font-weight: 500;
        cursor: pointer;
        text-decoration: none;
        color: black;
    }
}
</style>