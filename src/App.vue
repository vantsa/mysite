<template>
  <v-app>
    <v-main>
      <MainComponent/>
      <AboutSection/>
      <!-- <ResumeSection/>
      <PortfolioSection/>
      <ContactSection/>
      <FooterSection/> -->
    </v-main>
  </v-app>
</template>

<script>
import MainComponent from './components/MainComponent';
import AboutSection from './components/AboutSection';
import ResumeSection from './components/ResumeSection';
import PortfolioSection from './components/PortfolioSection';
import ContactSection from './components/ContactSection';
import FooterSection from './components/FooterSection';

export default {
  name: 'App',

  components: {
    MainComponent,
    AboutSection,
    ResumeSection,
    PortfolioSection,
    ContactSection,
    FooterSection,
  },

  data: () => ({
    //
  }),
};
</script>


<style scoped>
@font-face {
  font-family: "TitilliumWeb-Regular";
  src: local("TitilliumWeb-Regular"),
   url(assets/fonts/TitilliumWeb-Regular.ttf) format("truetype");
}
@font-face {
  font-family: "TitilliumWeb-Black";
  src: local("TitilliumWeb-Black"),
   url(assets/fonts/TitilliumWeb-Black.ttf) format("truetype");
}
@font-face {
  font-family: "TitilliumWeb-Bold";
  src: local("TitilliumWeb-Bold"),
   url(assets/fonts/TitilliumWeb-Bold.ttf) format("truetype");
}
@font-face {
  font-family: "TitilliumWeb-Light";
  src: local("TitilliumWeb-Light"),
   url(assets/fonts/TitilliumWeb-Light.ttf) format("truetype");
}
</style>