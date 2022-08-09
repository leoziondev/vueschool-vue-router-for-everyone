<template>
  <div id="app">
    <div id="nav">
      <h1>Vue<span>Travel</span></h1>
      <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/brazil">Brazil</router-link>
        <router-link to="/hawaii">Hawaii</router-link>
        <router-link to="/jamaica">Jamaica</router-link>
        <router-link to="/panama">Panama</router-link>
      </nav>
    </div>
    <router-view />
  </div>
</template>

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
a:hover,
#nav a:hover {
  color: #42b983;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 30px;
  background: white;
}

#nav h1 {
  font-size: 1.6rem;
}

#nav h1 span {
  color: #42b983;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 10px;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
