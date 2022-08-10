<template>
  <div id="nav-header">
    <h1>Vue<span>Travel</span></h1>
    <nav id="nav">
      <ul class="nav-links">
        <li class="nav-link-item">
          <router-link to="/">Home</router-link>
        </li>
        <li
          v-for="destination in destinations"
          :key="destination.name"
          class="nav-link-item"
        >
          <router-link
            :to="{
              name: 'DestinationDetails',
              params: { id: destination.id },
            }"
          >
            {{ destination.name }}
          </router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import store from "@/store";

export default {
  data() {
    return {
      destinationId: this.$route.params.id,
      destinations: store.destinations,
    };
  },
};
</script>

<style scoped>
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

#nav .nav-links {
  list-style: none;
  display: flex;
  gap: 10px;
}

#nav .nav-link-item {
  font-weight: bold;
  color: #2c3e50;
}

#nav .nav-link-item:hover {
  color: #42b983;
}

#nav .nav-link-item a.router-link-exact-active {
  color: #42b983;
}
</style>
