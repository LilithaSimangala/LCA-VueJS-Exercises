<template>
  <header class="header">
    <h1>Cooking Masterclass</h1>

    <div class="wishlist">
      ❤️ Wishlist: {{ wishlistCount }}
    </div>
  </header>
</template>

<script>
export default {
  props: ["wishlistCount"]
}
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #8B4513;
  color: white;
  padding: 20px;
}

.wishlist {
  font-weight: bold;
}
</style>