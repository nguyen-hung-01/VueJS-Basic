<script setup>
import product1Image from '../../assets/images/product1.jpg'
import product2Image from '../../assets/images/product2.jpg'
import product3Image from '../../assets/images/product3.jpg'

const data = [
  {
    id: 1,
    img: product1Image,
    name: 'Iphone 20 pro max',
    desc: 'Điện thoại thông minh được trang bị những tính năng cơ bản như một chiếc laptop giúp bạn có thể học tập và làm việc từ xa như soạn thảo văn bản, tra từ điển, call video học online hay họp, tìm kiếm thông tin trên internet,...',
    price: '29.000.000đ',
  },
  {
    id: 2,
    img: product2Image,
    name: 'Samsung Galaxy 99',
    desc: 'Điện thoại thông minh được trang bị những tính năng cơ bản như một chiếc laptop giúp bạn có thể học tập và làm việc từ xa như soạn thảo văn bản, tra từ điển, call video học online hay họp, tìm kiếm thông tin trên internet,...',
    price: '25.000.000đ',
  },
  {
    id: 3,
    img: product3Image,
    name: 'Redmi note 30 pro',
    desc: 'Điện thoại thông minh được trang bị những tính năng cơ bản như một chiếc laptop giúp bạn có thể học tập và làm việc từ xa như soạn thảo văn bản, tra từ điển, call video học online hay họp, tìm kiếm thông tin trên internet,...',
    price: '38.000.000đ',
  },
]
</script>

<template>
  <div v-for="product in data" :key="product.id" class="item">
    <img :src="product.img" :alt="product.name" />
    <div class="name-product">{{ product.name }}</div>
    <div class="desc-product">{{ product.desc }}</div>
    <div class="price-product">{{ product.price }}</div>
    <button>Mua ngay</button>
  </div>
</template>

<style scoped>
.item {
  border: 1px solid #ddd;
  padding: 16px;
  margin-bottom: 16px;
  text-align: center;
}
.item img {
  height: 180px;
  width: 260px;
  object-fit: cover;
  object-position: center;
}
.name-product {
  font-weight: bold;
  margin: 8px 0;
}
.desc-product {
  margin: 8px 0;
  font-size: 14px;
}
.price-product {
  color: red;
  font-size: 18px;
  margin: 8px 0;
}
button {
  padding: 8px 16px;
  background-color: #4caf50;
  color: white;
  border: none;
  cursor: pointer;
}
</style>
