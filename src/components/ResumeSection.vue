<template>
  <div class="bg">
    <div class="content">
      <div class="slide-in-container" ref="slideInContainer">
      <v-row justify="center">
        <v-col align="center">
          <v-btn
            elevation="2"
            rounded
            x-large
            class="resume"
            @click="openResume"
            >RESUME</v-btn
          >
        </v-col>
      </v-row>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ResumeSection",
     mounted() {
    window.addEventListener('scroll', this.checkSlide);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.checkSlide);
  },
  methods: {
    checkSlide() {
      const slideInContainer = this.$refs.slideInContainer;
      const slideInTop = slideInContainer.getBoundingClientRect().top;
      const windowHeight = window.innerHeight;

      if (slideInTop < windowHeight) {
        slideInContainer.classList.add('show');
      } else {
        slideInContainer.classList.remove('show');
      }
    },
    openResume(){
      window.open("https://drive.google.com/file/d/1OoZJ45DPw-XmVcBCpri3cklcbuv-VCE1/view?usp=sharing")
    }
  }
};
</script>

<style scoped>
.bg {
  width: 100%;
  background-color: #001b3b;
  margin-top: -1%;
}
.content{
    padding: 5% 0% 4% 0%;
    width: 70%;
    margin: 0 auto;
    border-bottom: 0.5rem solid white;
}
.resume{
  font-size: 1.8rem;
  text-decoration: none;
  font-family: 'TitilliumWeb-Bold';
  width: 30%;
  color: #001b3b;
  letter-spacing: 3px;
}
.line-col{
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 25%;
}
.line{
    background-color: red;
    height: 5px;
    border-radius: 50px;
}
.v-btn:hover {
  transform: translateY(-4px);
  box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.2);
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
