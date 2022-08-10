<template>
  <section class="destination">
    <div class="destination-cover">
      <img
        :src="require(`@/assets/${destination.image}`)"
        :alt="destination.name"
      />
    </div>
    <div class="destination-details">
      <h1>{{ destination.name }}</h1>
      <p>{{ destination.description }}</p>
    </div>
  </section>
</template>

<script>
import store from "@/store.js";

export default {
  data() {
    return {
      destinationId: this.$route.params.id,
    };
  },
  computed: {
    destination() {
      return store.destinations.find(
        (destination) => destination.id === this.destinationId
      );
    },
  },
};
</script>

<style scoped>
.destination {
  width: 1140px;
  margin: 50px auto;
  display: flex;
  justify-content: space-between;
}

.destination-cover {
  width: 400px;
}

.destination-cover img {
  width: 100%;
  object-fit: cover;
}

.destination-details {
  flex: 1;
  margin: 0 40px;
  text-align: left;
}

p {
  font-size: 1.4rem;
  line-height: 1.9rem;
  margin-top: 20px;
}
</style>
