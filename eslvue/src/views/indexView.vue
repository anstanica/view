<!-- eslint-disable prettier/prettier -->
<script lang="ts">
import { useCounterStore } from "@/stores/counter";
import { storeToRefs } from "pinia";

export default {
  setup() {
    const counterStore = useCounterStore();
    const { count, doubleCount } = storeToRefs(counterStore);
    const newCount = () => {
      counterStore.increment();
    };

    const lisCount = [count, doubleCount];
    const books = [
      {
        title: "The Awakening",
        author: "Kate Chopin",
        language: "English",
        Image: "",
      },
      {
        title: "City of Glass",
        author: "Paul Auster",
        language: "English",
        Image: "",
      },
      {
        title: "The Awakening",
        author: "Kate Chopin",
        language: "English",
        Image: "",
      },
      {
        title: "City of Glass",
        author: "Paul Auster",
        language: "English",
        Image: "",
      },
      {
        title: "The Awakening",
        author: "Kate Chopin",
        language: "English",
        Image: "",
      },
      {
        title: "City of Glass",
        author: "Paul Auster",
        language: "English",
        Image: "",
      },
    ];

    return {
      count,
      doubleCount,
      newCount,
      books,
      lisCount,
    };
  },
};
</script>
<template>

  <div class="flex flex-col container">
    <p>Count: {{ count }}</p>
    <p>Double Count: {{ doubleCount }}</p>

<!-- add vue video -->
    <video width="320" height="240" controls class="aspect-video">
      <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
      <source src="https://www.w3schools.com/html/mov_bbb.ogg" type="video/ogg">
      Your browser does not support the video tag.
    </video>
    <button @click="newCount" class="btn-primary ">count is: {{ count }}</button>
    <ul>
      <li v-for="item in lisCount" class="list-item ">
        author list: {{ item }}
        <!-- title list: {{ book.title }} -->
      </li>
      
      <li v-for="book in books" class="flex">
       Tile list: {{ book.title }} Title list: {{ book.title }}
        <img :src="book.Image" alt="book image" class="flex-auto" width="42px"/>

      </li>
    </ul>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
