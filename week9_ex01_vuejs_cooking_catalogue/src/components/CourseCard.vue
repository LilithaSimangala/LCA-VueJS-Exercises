<template>
  <div class="card">
    <h2>{{ course.title }}</h2>

    <p><strong>Chef:</strong> {{ course.chef }}</p>

    <p><strong>Level:</strong> {{ course.level }}</p>

    <p><strong>Price:</strong> R{{ course.price }}</p>

    <p
      v-if="!course.available"
      class="sold-out"
    >
      SOLD OUT
    </p>

    <button
      @click="saveCourse"
      :disabled="!course.available"
    >
      Save to Wishlist
    </button>
  </div>
</template>

<script>
export default {
  props: ["course"],

  methods: {
    saveCourse() {
      this.$emit("add-to-wishlist");
    }
  }
}
</script>

<style>
.card {
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 20px;
  width: 250px;
}

.sold-out {
  color: red;
  font-weight: bold;
}

button {
  margin-top: 10px;
  padding: 10px;
}
</style>