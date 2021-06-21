<template>
  <div class="login">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Login />
  </div>
</template>

<script>

import Login from "@/components/Login.vue";
export default {
  name: "Login",
  components: {
    Login,
  },
};
</script>
