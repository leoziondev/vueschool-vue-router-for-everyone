<template>
  <span class="go-back">
    <button @click="goBack">
      <svg
        width="20px"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
        stroke-width="2"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M11 17l-5-5m0 0l5-5m-5 5h12"
        />
      </svg>
      Go back
    </button>
  </span>
</template>

<script>
export default {
  methods: {
    goBack() {
      return this.$router.go(-1);
    },
  },
};
</script>

<style scoped>
.go-back {
  position: absolute;
  display: flex;
  left: 0px;
  top: -33px;
}

button {
  min-width: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 0;
  cursor: pointer;
  background: transparent;
  color: #42b983;
  font-weight: bold;
}

button svg {
  margin-right: 5px;
}

@media (max-width: 1024px) {
  .go-back {
    top: 20px;
    left: 20px;
    background: white;
    padding: 5px 10px;
    border-radius: 25px;
  }
}
</style>
