<script setup>
import { ref } from 'vue';

const count1 = ref(0);
const count2 = ref(0);

const dicrementCount = (targetCount) => {
    if (targetCount === 1) {
        targetCount = count1;
    }
    else {
        targetCount = count2;
    }
    if (targetCount.value > 0) {
        targetCount.value--;
    }
}
</script>

<template>
    <div class="container">
        <p class="count-text">
            Собрано на лечение: 
            <span class="count-value">{{ count1 }} &#8381;</span>
        </p>
        <div class="container-buttons">
            <button class="container-button" @click="dicrementCount(1)">-</button>
            <button class="container-button" @click="count1++">+</button>
        </div>
    </div>
    <div class="container">
        <p class="count-text">
            Собрано на PlayStation 6: 
            <span class="count-value">{{ count2 }} &#8381;</span>
        </p>
        <div class="container-buttons">
            <button class="container-button" @click="dicrementCount(2)">-</button>
            <button class="container-button" @click="count2++">+</button>
        </div>
    </div>
</template>

<style scoped>

.container {
  margin: 50px auto; 
  padding: 5px;
  text-align: center;
}

.count-text {
  margin-top: 50px;
  font-size: 2.2em;
}

.count-value {
  color: gold;
}

.container-button {
  padding: 3em;
  font-size: 2em;
  background-color: rgb(224, 224, 224);
  border-radius: 0.5em;
  border: 0;
  margin: 20px 10px 0px 10px;
}

</style>