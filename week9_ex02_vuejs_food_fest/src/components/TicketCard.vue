<template>
  <div class="card" :class="{ featured: ticket.featured }">
    <h2>{{ ticket.name }}</h2>

    <p class="price">R{{ ticket.price }}</p>

    <ul>
      <li v-for="(b, index) in ticket.benefits" :key="index">
        {{ b }}
      </li>
    </ul>

    <button @click="toggleFavourite">
      ❤️ Favourite ({{ ticket.favourites }})
    </button>
  </div>
</template>

<script>
export default {
  props: ["ticket"],

  methods: {
    toggleFavourite() {
      this.ticket.favourites++;
    }
  }
};
</script>

<style>
.card {
  border: 1px solid #ddd;
  padding: 20px;
  margin: 10px;
  width: 250px;
}

.featured {
  border: 2px solid gold;
  background: #fff8dc;
}

.price {
  font-size: 20px;
  font-weight: bold;
}
</style>