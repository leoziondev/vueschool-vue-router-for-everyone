<template>
  <section class="experience-container">
    <div class="experience">
      <div class="experience-cover">
        <img
          :src="require(`@/assets/${experience.image}`)"
          :alt="experience.name"
        />
      </div>
      <div class="experience-details">
        <h4><span>Experiences:</span> {{ experience.name }}</h4>
        <p>{{ experience.description }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import store from "@/store.js";

export default {
  props: {
    slug: {
      type: String,
      required: true,
    },
    experienceSlug: {
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
    experience() {
      return this.destination.experiences.find(
        (experience) => experience.slug === this.experienceSlug
      );
    },
  },
};
</script>

<style scoped>
.experience-container {
  margin-top: 50px;
}
.experience {
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 50px;
  background: white;
  border-radius: 8px;
  padding: 30px;
  box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.03);
}

.experience-cover {
  width: 400px;
}

.experience-cover img {
  width: 100%;
  object-fit: cover;
}

.experience-details {
  flex: 1;
  margin: 0 40px;
  text-align: left;
}

.experience-details h4 {
  font-size: 1.5rem;
  font-weight: bold;
}

.experience-details h4 span {
  color: #42b983;
}

.experience-details p {
  font-size: 1.2rem;
  line-height: 1.7rem;
  margin-top: 20px;
  color: #567a9d;
}

@media (max-width: 1024px) {
  .experience {
    display: flex;
    flex-direction: column;
  }

  .experience-details {
    margin: 0;
  }

  .experience-cover {
    width: 100%;
    max-height: 420px;
    overflow: hidden;
    margin-bottom: 30px;
  }
}
</style>
