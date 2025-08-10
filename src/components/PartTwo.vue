<script setup>
import { computed, reactive } from 'vue'

const usersList = reactive([
  {
    id: 1,
    name: 'Sarah',
    age: 30,
    books: [
      {
        title: 'Lorem ipsum',
        numOfPages: 352,
      },
      {
        title: 'Totam perspiciatis',
        numOfPages: 3057,
      },
      {
        title: 'Distin lipsum',
        numOfPages: 120,
      },
    ],
  },
  {
    id: 2,
    name: 'Olivier',
    age: 14,
    books: [
      {
        title: 'Distinctio',
        numOfPages: 873,
      },
      {
        title: 'Totam perspiciatis',
        numOfPages: 3057,
      },
    ],
  },
  {
    id: 3,
    name: 'Sam',
    age: 42,
    books: [
      {
        title: 'Numquam volup',
        numOfPages: 1309,
      },
      {
        title: 'Lorem ipsum',
        numOfPages: 479,
      },
      {
        title: 'Ipsum soluta',
        numOfPages: 1468,
      },
      {
        title: 'Voluptatibus',
        numOfPages: 3801,
      },
    ],
  },
])

const numberOfBook = computed(() => {
  let total = 0
  for (let i = 0; i < usersList.length; i++) {
    total += usersList[i].books.length
  }
  return total
})

const numberOfPage = computed(() => {
  let total = 0
  for (let i = 0; i < usersList.length; i++) {
    for (let j = 0; j < usersList[i].books.length; j++) {
      total += usersList[i].books[j].numOfPages
    }
  }
  return total
})

const addMember = () => {
  usersList.push({
    id: 4,
    name: 'John',
    age: 33,
    books: [
      {
        title: 'Lorem ipsum',
        numOfPages: 352,
      },
      {
        title: 'Totam perspiciatis',
        numOfPages: 3057,
      },
    ],
  })
}
</script>

<template>
  <section>
    <p>
      Le groupe de lecture compte <span>{{ usersList.length }}</span> membres
    </p>
    <p>
      A eux <span>{{ usersList.length }}</span
      >, ils ont lu <span>{{ numberOfBook }}</span> livres pour un total de
      <span>{{ numberOfPage }}</span>
      pages
    </p>
    <button @click="addMember">Ajouter un membre</button>
  </section>
</template>

<style scoped>
span {
  color: orange;
  font-weight: bold;
}

button {
  background: transparent;
  color: orange;
  border: 2px solid orange;
  padding: 10px 15px;
  border-radius: 5px;
  font-size: 16px;
}
</style>
