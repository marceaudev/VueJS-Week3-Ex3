<script setup>
import { computed, ref } from 'vue'

const user = {
  firstName: 'Toto',
  lastName: 'Smith',
}

const actualHours = ref(new Date().getHours())

const displayHoursMessage = computed(() => {
  let message = ''
  if (actualHours.value < 12) {
    message = 'Bonjour'
  } else if (actualHours.value < 18) {
    message = 'Bon après-midi'
  } else {
    message = 'Bonsoir'
  }
  return message + ', ' + user.firstName + ' ' + user.lastName
})
</script>

<template>
  <section>
    <p>{{ displayHoursMessage }}</p>
    <div>
      <button @click="actualHours = 3">Heure matin</button>
      <button @click="actualHours = 14">Heure après-midi</button>
      <button @click="actualHours = 21">Heure soir</button>
    </div>
  </section>
</template>

<style scoped>
div {
  display: flex;
  gap: 20px;
}

button {
  background: transparent;
  color: green;
  border: 2px solid green;
  padding: 10px 15px;
  border-radius: 5px;
  font-size: 16px;
}
</style>
