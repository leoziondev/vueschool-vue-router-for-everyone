<template>
  <div id="nav-header">
    <h1>Vue<span>Travel</span></h1>
    <nav id="nav">
      <span class="mobile-menu" @click="showMenu">
        <svg
          width="25px"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </span>
      <ul class="nav-links">
        <li class="nav-link-item" @click="showMenu">
          <router-link to="/">Home</router-link>
        </li>
        <li
          v-for="destination in destinations"
          :key="destination.name"
          @click="showMenu"
          class="nav-link-item"
        >
          <router-link
            :to="{
              name: 'DestinationDetails',
              params: { slug: destination.slug },
            }"
          >
            {{ destination.name }}
          </router-link>
        </li>
      </ul>
      <ul class="nav-links-mobile" v-if="isVisible">
        <li class="nav-link-item" @click="showMenu">
          <router-link to="/">Home</router-link>
        </li>
        <li
          v-for="destination in destinations"
          :key="destination.name"
          @click="showMenu"
          class="nav-link-item"
        >
          <router-link
            :to="{
              name: 'DestinationDetails',
              params: { slug: destination.slug },
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
      destinations: store.destinations,
      isVisible: true,
    };
  },
  methods: {
    showMenu() {
      this.isVisible = !this.isVisible;
    },
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
  position: relative;
}

#nav-header .mobile-menu {
  display: none;
  cursor: pointer;
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

#nav .nav-links-mobile {
  display: none;
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

@media (max-width: 560px) {
  #nav-header .mobile-menu {
    display: block;
  }

  #nav .nav-links {
    display: none;
  }

  #nav .nav-links-mobile {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
    padding: 15px;
    position: absolute;
    bottom: -160px;
    left: 0;
    z-index: 999;
    width: 100%;
    background: white;
    border-top: 1px solid #f8fafc;

    list-style: none;
  }
}
</style>
