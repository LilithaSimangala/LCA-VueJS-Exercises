<template>
  <div class="card">
    <h3>{{ classItem.name }}</h3>

    <p><strong>Coach:</strong> {{ classItem.coach }}</p>
    <p><strong>Date:</strong> {{ classItem.date }}</p>
    <p><strong>Time:</strong> {{ classItem.time }}</p>
    <p><strong>Capacity:</strong> {{ classItem.capacity }}</p>

    <button @click="$emit('delete')">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  props: {
    classItem: Object
  }
}
</script>

<style>
.card {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>