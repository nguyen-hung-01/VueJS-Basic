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
      <div class="logo">
        <img src="../../assets//images//lab2/logo-tiki.png" alt="" />
      </div>
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
.logo {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}
.logo img {
  width: 100px;
}
</style>
