<script setup>
import { ref, reactive, onMounted, computed, onUnmounted } from 'vue'
import StarIcon from './StarIcon.vue'

const products = reactive([])

const loadProducts = async () => {
  try {
    const reponsive = await fetch('../../../public/products.json')
    if (!reponsive.ok) throw new Error()
    const data = await reponsive.json()
    products.push(...data)
  } catch (error) {
    alert('Lỗi khi tải dữ liệu sản phẩm')
  }
}
onMounted(loadProducts)

const deliveryDate = (deliveryTime = 3) => {
  const today = new Date()
  const daysOfWeek = [
    'Chủ nhật',
    'Thứ 2',
    'Thứ 3',
    'Thứ 4',
    'Thứ 5',
    'Thứ 6',
    'Thứ 7',
  ]

  const dayOfWeek = daysOfWeek[(today.getDay() + deliveryTime) % 7]

  today.setDate(today.getDate() + deliveryTime)
  const day = today.getDate()
  const month = today.getMonth() + 1

  return `Giao ${dayOfWeek}, ${day}/${month}`
}

const formatPrice = price => new Intl.NumberFormat('vi-VN').format(price)

let idTimeout = null
let idImage = ref(0)
const caroselImage = () => {
  console.log('onMounted')
  idTimeout = setInterval(() => {
    console.log('idImage: ', idImage)
    if (idImage.value >= 2) {
      idImage.value = 0
    } else {
      idImage.value += 1
    }
  }, 3000)
}
onMounted(caroselImage)
onUnmounted(() => clearInterval(idTimeout))
</script>

<template>
  <div class="product-card" v-for="product in products" :key="product.id">
    <div class="imgs">
      <img :src="product?.images[idImage]" :alt="product.name" />
      <div class="tags">
        <div v-if="product.tags.topDeal" class="tag">
          <img src="../../assets//images/lab2/top-deal.png" alt="" />
        </div>
        <div v-if="product.tags.freeShip" class="tag">
          <img src="../../assets//images/lab2/freeship-xtra.png" alt="" />
        </div>
        <div v-if="product.tags.official" class="tag">
          <img src="../../assets//images/lab2/chinh-hang.png" alt="" />
        </div>
      </div>
    </div>
    <div class="product-info">
      <p class="name">{{ product.name }}</p>
      <div class="rating-sold">
        <div class="rating">
          <span v-for="i in product.rating" :key="i"><StarIcon /></span>
        </div>
        <p class="sold">Đã bán {{ product.sold }}</p>
      </div>
      <p class="current-price">
        {{ formatPrice(product.originalPrice * (1 - product.discount * 0.01))
        }}<sup>đ</sup>
      </p>
      <div class="origin-discount">
        <span class="discount">-{{ product.discount }}%</span>
        <span class="origin-price"
          >{{ formatPrice(product.originalPrice) }}<sup>đ</sup></span
        >
      </div>
      <p class="origin">Made in {{ product.origin }}</p>
      <div class="delivery-time">{{ deliveryDate() }}</div>
    </div>
  </div>
</template>

<style scoped>
.product-card {
  border: 1px solid rgb(227, 227, 227);
  border-radius: 8px;
  background: rgb(255, 255, 255);
  color: rgb(36, 36, 36);
  overflow: hidden;
  transition: 0.2s ease;
  cursor: pointer;
  font-size: 14px;
}
.product-card:hover {
  box-shadow: 3px 3px 7px #e3e3e3;
  transform: translateY(-2px);
}
.product-info {
  padding: 0 10px;
}
.name {
  color: #27272a;
  font-weight: 500;
  line-height: 140%;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  overflow: hidden;
  text-overflow: ellipsis;
  min-height: 2.8em;
  margin-top: 6px;
}
.imgs {
  height: 196px;
  position: relative;
  overflow: hidden;
}
.imgs img {
  width: 100%;
  height: 196px;
  object-fit: cover;
  object-position: center;
}
.current-price {
  color: rgb(255, 66, 78);
  font-size: 18px;
  line-height: 150%;
  font-weight: 500;
  margin-top: 5px;
}
.discount {
  color: black;
  font-weight: 400;
  display: inline-block;
  background-color: #ececec;
  padding: 1px 6px;
  border-radius: 6px;
  margin-right: 3px;
}
.origin-price {
  color: #808089;
  padding: 1px 5px;
  display: inline-block;
  font-weight: 400;
  text-decoration-line: line-through;
}
.origin {
  font-size: 12px;
  font-weight: 400;
  color: #4b4b4b;
  margin-top: 15px;
  margin-bottom: 5px;
}
.rating-sold {
  display: flex;
  align-items: center;
}
.sold {
  font-size: 13px;
  color: #808089;
  padding-top: 2px;
  padding-left: 5px;
  margin-left: 5px;
  border-left: 1px solid #cdcdcd;
}
.rating i {
  font-size: 12px;
  color: rgb(255, 196, 0);
}
.delivery-time {
  color: #808089;
  font-weight: 400;
  border-top: 1px solid #e0e0e0;
  padding: 8px 0;
}
.tags {
  position: absolute;
  bottom: -7px;
  left: 10px;
  display: flex;
}
.tags img {
  height: 35px;
}
</style>
