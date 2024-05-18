<template>
    <div class="shopping-cart">
      <h2>Keranjang Belanja</h2>
      <ul>
        <li v-for="(item, index) in cartItems" :key="index">{{ item.name }} - {{ item.price }}</li>
      </ul>
      <slot></slot>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ShoppingCart',
    props: {
      cartItems: Array
    }
  }
  </script>
  
  <style scoped>
  .shopping-cart {
  border: 1px solid #000;
  padding: 10px;
  margin: 20px;
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.6);
  border-radius: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  padding: 5px 0;
}
  </style>
  