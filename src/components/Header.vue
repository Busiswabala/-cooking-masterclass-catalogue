<template>
  <nav>
    <div class="brand">Cooking Masterclass Catalogue</div>

    <div class="wishlist">Wishlist: {{ wishlistCount }}</div>
  </nav>
</template>

<script setup>
defineProps({
  wishlistCount: Number,
});
</script>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.25rem 1.5rem;
  background: #faf1d9;
  color: #102a43;
  border-bottom: 1px solid #f1dfb7;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  z-index: 50;
  backdrop-filter: blur(8px);
}

.brand {
  font-size: 1.2rem;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.wishlist {
  font-size: 0.95rem;
  color: #334e68;
}
</style>
