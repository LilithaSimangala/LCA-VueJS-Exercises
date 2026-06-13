<template>
  <div class="cart">
    <h2>Your Cart</h2>

    <div v-if="cart.length === 0">
      Your cart is empty.
    </div>

    <div v-else>
      <CartItem
        v-for="item in cart"
        :key="item.id"
        :item="item"
        @increase="$emit('increase-quantity', item)"
        @decrease="$emit('decrease-quantity', item)"
        @remove="$emit('remove-item', item)"
      />

      <div class="summary">
        <p><strong>Subtotal:</strong> R{{ subtotal.toFixed(2) }}</p>
        <p><strong>Tax (15%):</strong> R{{ tax.toFixed(2) }}</p>
        <p><strong>Total:</strong> R{{ grandTotal.toFixed(2) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import CartItem from './CartItem.vue'

export default {
  components: {
    CartItem
  },

  props: {
    cart: {
      type: Array,
      required: true
    },
    subtotal: Number,
    tax: Number,
    grandTotal: Number
  }
}
</script>