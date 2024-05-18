<template>
    <div class="product-list">
      <h2>Daftar Produk</h2>
      <ProductItem 
        v-for="product in products" 
        :key="product.id" 
        :product="product" 
        @add-to-cart="handleAddToCart" 
      />
    </div>
  </template>
  
  <script>
  import ProductItem from './productitem.vue';
  
  export default {
    name: 'ProductList',
    components: {
      ProductItem
    },
    props: {
      products: Array
    },
    methods: {
      handleAddToCart(product) {
        this.$emit('add-to-cart', product);
      }
    }
  }
  </script>
  
  <style scoped>
  .product-list {
    display: flex;
    flex-wrap: wrap;
  }
  </style>
  