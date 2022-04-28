<template>
  <div class="product">
    <div class="product-details">
      <img src="../assets/index.jpeg" alt="" />
      <div>
        <h2>{{ shoesName }}</h2>
        <p>{{ detail }}</p>
        <p>{{ price }} €</p>

        <button @click="addTocart">ajouter au panier</button>
        <button @click="initial">vider le panier</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cart",

  data() {
    return {
      shoesName: "Nike Air Force 1 High",
      detail: "Chaussures personnalisables pour Homme",
      price: 149.99,
    };
  },

  methods: {
    addTocart: function () {
      this.$emit("addcart");
    },
    initial: function () {
      this.$emit("delete-cart");
    },
  },
};
</script>

<style>
body {
  background: none;
}
.product {
}
.product-details {
  display: flex;
  justify-content: space-between;
  padding: 0px;
  margin: 20px;
}
.product-details div {
  text-align: left;
  padding: 0px 10px;
  margin: 0px;
}
.product-details img {
  width: 40%;
  background: none;
}
h2 {
  color: #d35400;
}
button {
  transition: 0.2s;
  font-size: 1em;
  border: none;
  border-radius: 3px;
  height: 40px;
  background-color: black;
  color: white;
  cursor: pointer;
  margin: 5px;
  width: 150px;
}
button:hover {
  transition: 0.2s;
  font-size: 1.1em;
  border: none;
  border-radius: 5px;
  height: 40px;
  background-color: #d35400;
  color: white;
  cursor: pointer;
}
</style>