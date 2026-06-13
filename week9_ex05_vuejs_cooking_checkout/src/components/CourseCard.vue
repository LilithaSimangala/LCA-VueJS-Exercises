<template>
  <div class="course-card">
    <h3>{{ course.name }}</h3>

    <p><strong>Instructor:</strong> {{ course.instructor }}</p>
    <p><strong>Price:</strong> R{{ course.price }}</p>
    <p><strong>Spaces left:</strong> {{ course.spaces }}</p>

    <button
      :disabled="course.spaces === 0"
      @click="addToCart"
    >
      {{ course.spaces === 0 ? "Sold Out" : "Add to Cart" }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    course: {
      type: Object,
      required: true
    }
  },

  methods: {
    addToCart() {
      this.$emit("add-to-cart", this.course)
    }
  }
}
</script>