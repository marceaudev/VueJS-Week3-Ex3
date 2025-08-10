<script setup>
import { computed, reactive } from 'vue'

const numberArray = reactive([76, 876, 467, 2, 67, 3, 90, 7, 678])

const averageCalc = computed(() => {
  let total = 0
  for (let i = 0; i < numberArray.length; i++) {
    total += numberArray[i]
  }
  return Number((total / numberArray.length).toFixed(2))
})

const addRandomNumber = () => {
  const randomNumber = Math.floor(Math.random() * 1000)
  numberArray.push(randomNumber)
}
</script>

<template>
  <section>
    <p>Moyenne du tableau : {{ numberArray }}</p>
    <p>{{ averageCalc }}</p>
    <button @click="addRandomNumber">Ajouter un nombre aléatoire</button>
  </section>
</template>

<style scoped>
p:last-of-type {
  font-weight: bold;
  color: rgb(110, 62, 223);
}

button {
  background: transparent;
  color: rgb(110, 62, 223);
  border: 2px solid rgb(110, 62, 223);
  padding: 10px 15px;
  border-radius: 5px;
  font-size: 16px;
}
</style>
