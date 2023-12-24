<template>
  <div class="loading-screen">
    <v-icon
      v-for="index in numberOfSnowflakes"
      :key="index"
      class="circular-falling-snowflake"
      :style="{ left: `${getRandomPosition()}%`, animationDelay: `${getRandomDelay()}s` }"
    >
      mdi-snowflake
    </v-icon>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numberOfSnowflakes: 400,
    };
  },
  methods: {
    getRandomPosition() {
      return Math.random() * 100;
    },
    getRandomDelay() {
      return Math.random() * 5; // Adjust the maximum delay time as needed
    },
  },
};
</script>

<style scoped>
.loading-screen {
  position: fixed;
  z-index: 999;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #071630;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.circular-falling-snowflake {
  position: absolute;
  color: white;
  font-size: 2rem;
  opacity: 0;
  animation: circularFall 3s linear infinite; 
}

@keyframes circularFall {
  0% {
    transform: translateY(-60vh);
    opacity: 0.5;
  }
  25% {
    opacity: 1;
  }
  100% {
    transform: translateY(100vh);
  }
}
</style>
