<template>
  <div id="app">
    <div id="nav-header">
      <h1>Vue<span>Travel</span></h1>
      <TheNavigation />
    </div>
    <router-view />
  </div>
</template>

<script>
import TheNavigation from "@/components/TheNavigation";

export default {
  components: {
    TheNavigation,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #f8fafc;
}
a {
  text-decoration: none;
  color: #2c3e50;
}
a:hover {
  color: #42b983;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav-header {
  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 30px;
  background: white;
}

#nav-header h1 {
  font-size: 1.6rem;
}

#nav-header h1 span {
  color: #42b983;
}
</style>
