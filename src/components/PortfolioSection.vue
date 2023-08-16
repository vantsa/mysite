<template>
  <div class="bg">
    <div class="content">
      <div class="slide-in-container" ref="slideInContainer">
        <h4>CHECK OUT MY PROJECTS</h4>
        <h4 class="st">ON GITHUB</h4>
        
        <v-row justify="center">
          <v-col align="center" @click="openWL">
            <div class="box">
              <img src="../assets/wl.jpg" />
              <p><strong>Weekend Lake Festival</strong><br />(HTML, CSS, JS)</p>
            </div>
          </v-col>
          <v-col align="center" @click="openLE">
            <div class="box">
              <img src="../assets/le.png" />
              <p><strong>Final Project</strong><br />(Vue.js, ASP .NET Core)</p>
            </div>
          </v-col>
          <v-col align="center" @click="openWS">
            <div class="box">
              <img src="../assets/ws.png" />
              <p><strong>Grocery store</strong><br />(Vue.js, PHP)</p>
            </div>
          </v-col>
        </v-row>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PortfolioSection",
  mounted() {
    window.addEventListener("scroll", this.checkSlide);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.checkSlide);
  },
  methods: {
    checkSlide() {
      const slideInContainer = this.$refs.slideInContainer;
      const slideInTop = slideInContainer.getBoundingClientRect().top;
      const windowHeight = window.innerHeight;

      if (slideInTop < windowHeight) {
        slideInContainer.classList.add("show");
      } else {
        slideInContainer.classList.remove("show");
      }
    },
    openWL() {
      window.open(
        "https://github.com/vantsa/Weekend-Lake-Festival-first-template"
      );
    },
    openLE() {
      window.open("https://github.com/vantsa/allamvizsga");
    },
    openWS() {
      window.open("https://github.com/istiballo/webprog_frontend_final");
    },
  },
};
</script>

<style scoped>
.bg {
  width: 100%;
  background-color: #001b3b;
}
.content {
  width: 100%;
  margin: 0 auto;
  padding-bottom: 7%;
  padding-top: 5%;
}
.box {
  transition: transform 1s ease;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}
h4 {
  color: white;
  font-family: Titilliumweb-Black;
  letter-spacing: 5px;
  font-size: 2.5rem;
  text-align: center;
  padding-top: 6%;
}
.st {
  padding-top: 0.5%;
  padding-bottom: 6%;
  font-size: 1rem;
  font-family: TitilliumWeb-Regular;
  letter-spacing: 1rem;
}
img {
  width: 104%;
  height: auto;
}
p {
  color: white;
  text-align: center;
  font-family: TitilliumWeb-Light;
  letter-spacing: 4px;
  padding: 1rem;
  font-size: 1rem;
}
.box:hover {
  cursor: pointer;
  transform: scale(1.1);
}
.slide-in-container {
  opacity: 0;
  transform: translateY(20%); 
  transition: opacity 1.5s ease, transform 1.5s ease; 
}
.slide-in-container.show {
  opacity: 1; 
  transform: translateY(0); 
}
</style>