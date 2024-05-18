<template>
  <div id="app">
    <h1>Toko Sederhana</h1>
    <ProductList :products="products" @add-to-cart="addToCart" />
    <ShoppingCart :cartItems="cart">
      <template v-slot:default>
        <p>Terimakasih!</p>
      </template>
    </ShoppingCart>
  </div>
</template>

<script>
import ProductList from './components/productlist.vue';
import ShoppingCart from './components/shoppingcart.vue';

export default {
  name: 'App',
  components: {
    ProductList,
    ShoppingCart
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Pantovel Adidass', description: 'Ukuran:38,39,40,41,42', price: 'Rp.1.000.000' },
        { id: 2, name: 'Tas ARMAGEDDON', description: 'Dari Kulit Buaya Asli ', price: 'Rp.20.000.000' },
        { id: 3, name: 'Honda HRV', description: 'Tes Drive Dulu', price: 'Rp.450.000.000' }
      ],
      cart: []
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* Menambahkan background image dan memastikan menyesuaikan layar */
  background-image: url('./assets/indomaret.jpg');
  background-size: cover; /* Menyesuaikan ukuran background agar cover seluruh layar */
  background-position: center; /* Memposisikan gambar di tengah */
  background-repeat: no-repeat; /* Mencegah pengulangan gambar */
  min-height: 100vh; /* Menjamin minimum tinggi adalah 100% dari tinggi viewport */
  padding: 20px;
}
</style>
