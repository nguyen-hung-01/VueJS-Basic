<script setup>
import ItemProduct from './ItemProduct.vue'
</script>

<template>
  <div class="exercise2">
    <h1>Product List</h1>
    <div class="list-product">
      <item-product />
    </div>
  </div>
</template>

<style scoped>
.list-product {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}
</style>
