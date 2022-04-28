<template>
  <div id="app">
    <h1>product</h1>
    <cart @addcart="updatecart" @delete-cart="deleteCart" />
    <p class="cart">Panier ({{ panier }})</p>
  </div>
</template>

<script>
import cart from "./components/cart.vue";
export default {
  name: "App",
  components: {
    cart,
  },
  data() {
    return {
      panier: 0,
    };
  },
  methods: {
    updatecart: function () {
      this.panier += 1;
    },
    deleteCart: function () {
      if (this.panier > 0) {
        this.panier -= 1;
      } else {
        alert("le panier est vide !");
      }
    },
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  position: relative;
}
.cart {
  position: absolute;
  top: 2px;
  right: 2px;
}
</style>
