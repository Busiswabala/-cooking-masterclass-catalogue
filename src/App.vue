<template>
  <Header :wishlistCount="wishlistCount" />

  <main>
    <CourseCard
      v-for="course in courses"
      :key="course.id"
      :course="course"
      @save="addToWishlist"
    />
  </main>
</template>

<script setup>
import { ref } from "vue";

import Header from "./components/Header.vue";
import CourseCard from "./components/CourseCard.vue";

import courses from "./data/courses";

const wishlistCount = ref(0);

function addToWishlist() {
  wishlistCount.value++;
}
</script>

<style>
body {
  margin: 0;
  font-family: Inter, Arial, sans-serif;
  background: #e8c792;
  color: #102a43;
}

main {
  padding: 120px 24px 24px;
  display: grid;
  grid-template-columns: repeat(3, minmax(250px, 1fr));
  gap: 24px;
}
</style>
