<template>
  <div class="main">
    <v-row no-gutters> 
      <v-col cols="12" md="6" sm="12">
        <div class="slide-in-container" ref="slideInContainer">
        <h3>About</h3>
        <div class="abouttext">
          <p>
            My name is Alpár Vántsa, and I have recently graduated from
            Sapientia University, where I studied Business Informatics in
            Miercurea Ciuc, Romania. I am excited to introduce myself and share
            my background and aspirations.
          </p>
          <p>
            I have a strong foundation in Business Informatics, which has
            equipped me with a blend of technical and business skills. During my
            studies, I gained hands-on experience in various aspects of
            technology and problem-solving, which has prepared me well for
            real-world challenges.
          </p>
          <p>
            I am enthusiastic about the possibility of
            <strong>relocating</strong> for work opportunities. I am
            committed to personal growth and believe that stepping out of my
            comfort zone is essential for professional development. I thrive in
            collaborative environments and enjoy working as part of a team to
            achieve common goals.
          </p>
          <p>
            One of my strengths is my ability to learn quickly and adapt to new
            situations. I am driven by curiosity and a desire to continually
            expand my knowledge and skill set. I am a proactive and dedicated
            individual who takes pride in delivering high-quality work.
          </p>
          <p>
            If there is a job opening that aligns with my skills and goals, I
            would greatly appreciate the opportunity to connect and discuss how
            I could contribute to your team. Please feel free to reach out to me
            at your convenience. Thank you for considering my interest, and I
            look forward to the possibility of working together.
          </p>
          <p class="signature">Vantsa</p>
        </div>
        </div>
      </v-col>
      <v-col cols="12" md="6" sm="12" align-self="center" align="center">
        <img src="../assets/vantsaa.jpg" />
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "AboutSection",
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
    }
  }
};
</script>

<style scoped>
.main {
  width: 100%;
}
h3 {
  text-align: center;
  font-family: TitilliumWeb-Black;
  font-size: 5rem;
  padding: 12%;
  color: #001B3B;
}
.abouttext {
  width: 70%;
  margin: 0 auto;
}
img{
  width: 100%;
  box-shadow: -20px 0px 65px 0px rgba(0, 0, 0, 0.74);
}
p{
  text-align: justify;
  margin-top: -2%;
  line-height: 1.8rem;
  font-family: TitilliumWeb-Regular;
  font-weight: 600;
  font-size: 1.1rem;
  letter-spacing: 1px;
  color: #001B3B;
}
p::first-letter{
  margin-left: 10%;
}
.signature{
  text-align: right;
  padding-top: 10%;
  font-style: italic;
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
@media screen and (max-width: 960px){
  .signature{
    margin-bottom: 10%;
  }
  img{
    width: 80%;
  }
  .abouttext{
    width: 85%;
  }
}
@media screen and (max-width: 600px){
  h3{
    font-size:4rem;
  }
  p{
    font-size: 0.9rem;
  }
}
</style>