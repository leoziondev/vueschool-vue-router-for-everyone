<template>
  <div class="dash">
    <h1>Welcome back {{ user }}</h1>
    <p>
      <router-link :to="{ name: 'invoices' }">Invoices</router-link>
    </p>
    <button @click="logOut" class="btn">Log out</button>
  </div>
</template>

<script>
import store from "@/store.js";

export default {
  data() {
    return {
      user: store.user,
    };
  },
  methods: {
    logOut() {
      store.user = null;
      this.$router.push("/");
    },
  },
};
</script>

<style scoped>
.dash {
  margin-top: 50px;
}

.dash a {
  color: #42b983;
  font-weight: bold;
  display: inline-block;
  margin-top: 20px;
}
</style>
