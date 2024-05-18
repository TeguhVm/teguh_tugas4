<template>
    <div class="product-item">
      <h3>{{ product.name }}</h3>
      <p>{{ product.description }}</p>
      <p>Harga: {{ product.price }}</p>
      <button @click="addToCart">Tambah ke Keranjang</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductItem',
    props: {
      product: Object
    },
    methods: {
      addToCart() {
        this.$emit('add-to-cart', this.product);
      }
    }
  }
  </script>
  
  <style scoped>
  .product-item {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
  text-align: left;
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.6);
  border-radius: 10px;
}

button {
  margin-top: 10px;
  padding: 5px 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
  </style>
  