<template>
  <div class="home">
    <h1>All destinations</h1>
    <div class="destinations">
      <div v-for="destination in destinations" :key="destination.name">
        <router-link :to="destination.slug">
          <h2>{{ destination.name }}</h2>
        </router-link>
        <figure>
          <router-link :to="destination.slug">
            <img
              :src="require(`@/assets/${destination.image}`)"
              :alt="destination.name"
            />
          </router-link>
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import store from "@/store.js";

export default {
  name: "Home",
  components: {},
  data() {
    return {
      destinations: store.destinations,
    };
  },
};
</script>
<style scoped>
.home {
  max-width: 1140px;
  margin: 50px auto;
}

.destinations {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  margin-top: 30px;
}

.destinations img {
  /* max-width: 200px; */
  width: 100%;
  object-fit: cover;
}

@media (max-width: 1024px) {
  .destinations {
    grid-template-columns: repeat(2, 1fr);
    padding: 0 20px;
  }
}

@media (max-width: 560px) {
  .destinations {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
