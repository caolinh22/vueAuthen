<template>
  <div class="login">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Product />
  </div>
</template>

<script>
import Product from "../components/Product.vue";
export default {
  name: "Account",
  components: {
    Product,
  },
};
