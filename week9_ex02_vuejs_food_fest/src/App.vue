<template>
  <header class="header">
    <h1>Cape Town Food Fest</h1>
    <p>Weekend food, music & culture celebration</p>
  </header>

  <div class="container">
    <TicketCard
      v-for="ticket in tickets"
      :key="ticket.id"
      :ticket="ticket"
    />
  </div>
</template>

<script>
import TicketCard from "./components/TicketCard.vue";
import { tickets } from "./data/tickets";

export default {
  components: {
    TicketCard
  },

  data() {
    return {
      tickets
    };
  }
};
</script>

<style>
.header {
  text-align: center;
  background: #222;
  color: white;
  padding: 20px;
}

.container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
