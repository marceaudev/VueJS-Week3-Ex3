<script setup>
import PartOne from './components/PartOne.vue'
import PartTwo from './components/PartTwo.vue'
import PartThree from './components/PartThree.vue'
</script>

<template>
  <main class="container">
    <h1>A vos calculs !</h1>
    <PartOne />
    <PartTwo />
    <PartThree />
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

h1 {
  font-size: 45px;
  font-weight: bold;
}
</style>
