<template>
  <div class="catalogue">
    <h2>Available Courses</h2>

    <div v-if="courses.length === 0">
      No courses available.
    </div>

    <div v-else class="course-grid">
      <CourseCard
        v-for="course in courses"
        :key="course.id"
        :course="course"
        @add-to-cart="$emit('add-to-cart', course)"
      />
    </div>
  </div>
</template>

<script>
import CourseCard from './CourseCard.vue'

export default {
  components: {
    CourseCard
  },

  props: {
    courses: {
      type: Array,
      required: true
    }
  }
}
</script>