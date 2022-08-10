<template>
  <div class="not-found">
    <h1>Not Found</h1>
    <p>Oops we couldn't find that page. Try going</p>
    <router-link :to="{ name: 'Home' }">Back to home</router-link>
  </div>
</template>

<style scoped>
.not-found {
  margin-top: 250px;
}

.not-found a {
  display: inline-block;
  margin-top: 25px;
  color: #42b983;
  font-weight: bold;
  border: 2px solid #42b983;
  padding: 5px 10px;
  border-radius: 25px;
}
</style>
