<script setup>
// import { defineProps } from "vue";  (In Vue 3,`defineProps` is a compiler macro and no longer needs to be imported.)
import { useRouter } from 'vue-router';

const router = useRouter();
const { quiz } = defineProps(["quiz"]);

const navigateToQuiz = () => {
  router.push(`/quiz/${quiz.id}`)
}

</script>

<template>
  <div class="card" @click="navigateToQuiz">
    <img :src="quiz.img" alt="" />
    <div class="card-text">
      <h2>{{ quiz.name }}</h2>
      <p>{{ quiz.questions.length }} questions</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: $shadow;
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;

  img {
    width: 100%;
    height: 190px;
    margin: 0;
  }

  .card-text {
    padding: 0 5px;
  }

  .card-text h2 {
    font-weight: bold;
  }
}
</style>
