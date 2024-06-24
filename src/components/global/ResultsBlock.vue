<script setup>
import { ref } from "vue";

// const results = [
//   {
//     imgURL: "./src/assets/img/Results/1.png",
//     name: "Маргарита",
//     text: " .... ",
//   },
//   {
//     imgURL: "./src/assets/img/Results/1.png",
//     name: "Жанна",
//     text: " .... ",
//   },
//   {
//     imgURL: "./src/assets/img/Results/2.png",
//     name: "Алиса",
//     text: " .... ",
//   },
//   {
//     imgURL: "./src/assets/img/Results/1.png",
//     name: "Светалана",
//     text: " .... ",
//   },
//   {
//     imgURL: "./src/assets/img/Results/1.png",
//     name: "Ирина",
//     text: " .... ",
//   },

//   {
//     imgURL: "./src/assets/img/Results/1.png",
//     name: "Яна",
//     text: " .... ",
//   },
// ];

async function getData() {
  const response = await fetch("./back/db/results.json");
  const data = await response.json();
  return data;
}

const results = ref([]);

getData().then((result) => (results.value = result));
</script>

<template>
  <section>
    <SectionHeader>Резульаты нашей работы</SectionHeader>
    <div class="grid grid-cols-3 gap-6 px-20">
      <ResultsItem
        v-for="(item, index) in results"
        :key="index"
        :result="item"
        :isFull="false"
      />
    </div>
  </section>
</template>
