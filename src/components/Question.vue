<script setup>

import { defineEmits } from 'vue';

const emit = defineEmits(["selectOption"]);

const { question } = defineProps(['question']);

const emitSelectedOption = (isCorrect) => {
    emit("selectOption", isCorrect)
};

</script>

<template>
    <div class="question-container">
        <h1 class="question">{{ question.text }}</h1>
    </div>
    <div class="options-container">
        <div v-for="option in question.options" :key="option.id" @click="emitSelectedOption(option.isCorrect)"
            class="option">
            <p class="option-label">{{ option.label }}</p>
            <div class="option-value">
                <p>{{ option.text }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.question-container {
    margin-top: 20px;

    .question {
        font-size: 40px;
        margin-bottom: 20px;
    }
}
.options-container {
    .option {
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;
        .option-label {
            border: 3px solid $secondary-color;
            width: 40px;
            height: 40px;
            font-size: 30px;
            font-weight: 500;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 100%;
            margin-right: 10px;
        }
        .option-value {
            background-color: $tertiary-color;
            width: 100%;
            font-size: 30px;
            padding: 0 20px;
            border-radius: 15px;
            display: flex;
            align-items: center;
        }
    }

}
</style>