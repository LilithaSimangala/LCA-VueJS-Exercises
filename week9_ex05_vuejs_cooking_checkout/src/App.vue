<template>
  <div class="container">
    <h1>Cooking Masterclass Checkout</h1>

    <div class="layout">
      <CourseCatalogue
        :courses="courses"
        @add-to-cart="addToCart"
      />

      <ShoppingCart
        :cart="cart"
        :subtotal="subtotal"
        :tax="tax"
        :grand-total="grandTotal"
        @increase-quantity="increaseQuantity"
        @decrease-quantity="decreaseQuantity"
        @remove-item="removeItem"
      />
    </div>
  </div>
</template>

<script>
import CourseCatalogue from './components/CourseCatalogue.vue'
import ShoppingCart from './components/ShoppingCart.vue'

export default {
  components: {
    CourseCatalogue,
    ShoppingCart
  },

  data() {
    return {
      courses: [
        {
          id: 1,
          name: "Italian Pasta Masterclass",
          instructor: "Chef Marco",
          price: 450,
          spaces: 5
        },
        {
          id: 2,
          name: "Sushi Basics",
          instructor: "Chef Aiko",
          price: 550,
          spaces: 3
        },
        {
          id: 3,
          name: "French Pastry Essentials",
          instructor: "Chef Pierre",
          price: 600,
          spaces: 0
        },
        {
          id: 4,
          name: "South African Braai Techniques",
          instructor: "Chef Thando",
          price: 400,
          spaces: 4
        }
      ],

      cart: []
    }
  },

  methods: {
    addToCart(course) {
      const cartItem = this.cart.find(
        item => item.id === course.id
      )

      if (course.spaces > 0) {
        if (cartItem) {
          cartItem.quantity++
        } else {
          this.cart.push({
            ...course,
            quantity: 1
          })
        }

        course.spaces--
      }
    },

    increaseQuantity(item) {
      const course = this.courses.find(
        course => course.id === item.id
      )

      if (course.spaces > 0) {
        item.quantity++
        course.spaces--
      }
    },

    decreaseQuantity(item) {
      const cartItem = this.cart.find(
        cartItem => cartItem.id === item.id
      )

      const course = this.courses.find(
        course => course.id === item.id
      )

      if (cartItem.quantity > 1) {
        cartItem.quantity--
      } else {
        this.removeItem(item)
      }

      course.spaces++
    },

    removeItem(item) {
      const course = this.courses.find(
        course => course.id === item.id
      )

      course.spaces += item.quantity

      this.cart = this.cart.filter(
        cartItem => cartItem.id !== item.id
      )
    }
  },

  computed: {
    subtotal() {
      return this.cart.reduce(
        (total, item) => total + (item.price * item.quantity),
        0
      )
    },

    tax() {
      return this.subtotal * 0.15
    },

    grandTotal() {
      return this.subtotal + this.tax
    }
  }
}
</script>