<template>
  <Header :wishlistCount="wishlistCount" />

  <div class="container">
    <CourseCard
      v-for="course in courses"
      :key="course.id"
      :course="course"
      @add-to-wishlist="increaseWishlist"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CourseCard from "./components/CourseCard.vue";
import { courses } from "./data/courses";

export default {
  components: {
    Header,
    CourseCard
  },
  data() {
    return {
      courses,
      wishlistCount: 0
    };
  },
  methods: {
    increaseWishlist() {
      this.wishlistCount++;
    }
  }
};
</script>

<style>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>