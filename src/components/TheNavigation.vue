<template>
  <nav id="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/brazil">Brazil</router-link>
    <router-link to="/hawaii">Hawaii</router-link>
    <router-link to="/jamaica">Jamaica</router-link>
    <router-link to="/panama">Panama</router-link>
  </nav>
</template>

<style scoped>
#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 10px;
}

#nav a:hover {
  color: #42b983;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
