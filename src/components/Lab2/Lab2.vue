<script setup>
import { ref } from 'vue'
import ProductCard from './ProductCard.vue'
</script>

<template>
  <div id="wrapper">
    <nav class="menu-top">
      <a href="#" class="active">Reactivity</a>
    </nav>
    <div class="content">
      <h1>Tiki.com</h1>
      <div class="product-list">
        <ProductCard />
      </div>
    </div>
  </div>
</template>

<style scoped>
.product-list {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 12px;
  padding: 15px;
  padding-bottom: 40px;
}
</style>
