
<script setup>
const { questionStatus, barPercentage } = defineProps(["questionStatus", "barPercentage"]);
</script>

<template>
    <header>
        <h4>Question {{ questionStatus }}</h4>
        <div class="bar">
            <div class="completion" :style="{ width: barPercentage }"></div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    margin-top: 20px;



    h4 {
        font-size: 30px;
    }

    .bar {
        width: 300px;
        height: 20px;
        border: 3px solid $primary-color;
        border-radius: 15px;

        .completion {
            height: 100%;
            width: 0%;
            border-radius: 15px;
            background-color: $secondary-color;

        }
    }
}
</style>