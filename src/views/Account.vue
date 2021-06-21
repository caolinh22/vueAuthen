<template>
  <div class="login">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Account />
  </div>
</template>

<script>

import Account from "@/components/Account.vue";
export default {
  name: "Account",
  components: {
    Account,
  },
};
</script>
