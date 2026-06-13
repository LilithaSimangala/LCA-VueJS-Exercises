<template>
  <div class="cart-item">
    <div class="info">
      <h4>{{ item.name }}</h4>
      <p>R{{ item.price }} x {{ item.quantity }}</p>
      <p><strong>Total:</strong> R{{ item.price * item.quantity }}</p>
    </div>

    <div class="controls">
      <button @click="$emit('decrease')">-</button>
      <span>{{ item.quantity }}</span>
      <button @click="$emit('increase')">+</button>
    </div>

    <button class="remove" @click="$emit('remove')">
      Remove
    </button>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  }
}
</script>