<template>
  <div class="container">
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
    <section class="experiences">
      <h2>Top experiences in {{ destination.name }}</h2>
      <div class="cards">
        <div
          v-for="experience in destination.experiences"
          :key="experience.slug"
          class="card"
        >
          <router-link
            :to="{
              name: 'experienceDetails',
              params: { experienceSlug: experience.slug },
            }"
          >
            <img
              :src="require(`@/assets/${experience.image}`)"
              :alt="experience.name"
            />
            <h3 class="card__text">
              {{ experience.name }}
            </h3>
          </router-link>
        </div>
      </div>
      <router-view :key="$route.path" />
    </section>
  </div>
</template>

<script>
import store from "@/store.js";

export default {
  data() {
    return {};
  },
  props: {
    slug: {
      type: String,
      required: true,
    },
  },
  computed: {
    destination() {
      return store.destinations.find(
        (destination) => destination.slug === this.slug
      );
    },
  },
};
</script>

<style scoped>
.container {
  width: 100%;
  max-width: 1400px;
  margin: 50px auto;
}

.destination {
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 50px;
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

.destination-details p {
  font-size: 1.4rem;
  line-height: 1.9rem;
  margin-top: 20px;
}

.cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 40px;
  margin-top: 50px;
}

.cards img {
  max-width: 100%;
}

.card {
  position: relative;
}

.card__text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  font-size: 1.5rem;
  font-weight: bold;
  text-decoration: none;
}

@media (max-width: 1280px) {
  .cards {
    padding: 0 20px;
  }
}

@media (max-width: 1024px) {
  .container {
    margin-top: 0;
  }
  .destination {
    display: flex;
    flex-direction: column;
  }

  .destination-cover {
    width: 100%;
    max-height: 420px;
    overflow: hidden;
    margin-bottom: 30px;
  }

  .cards {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 560px) {
  .cards {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
