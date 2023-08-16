<template>
  <div class="bg">
    <div class="content">
      <p class="name">JUNIOR SOFTWARE DEVELOPER</p>
      <p class="self">VÁNTSA</p>
      <p class="self">ALPÁR</p>
    </div>
      <v-row class="socials" justify="center">
      <v-col class="icon" cols="auto">
        <a href="https://www.linkedin.com/in/v%C3%A1ntsa-alp%C3%A1r-a6705a1b3/" target="_blank"><v-icon size="40px" color= "#EEE1C6">mdi-linkedin</v-icon></a>
      </v-col>
      <v-col class="icon" cols="auto">
        <a href="https://www.instagram.com/vantsaaa/" target="_blank"><v-icon size="40px" color= "#EEE1C6">mdi-instagram</v-icon></a>
      </v-col>
      <v-col class="icon" cols="auto">
        <a href="https://github.com/vantsa" target="_blank"><v-icon size="40px" color= "#EEE1C6">mdi-github</v-icon></a>
      </v-col>
    </v-row>
    <div class="scroll">
    <v-icon class="arrow" size="4rem" color= "white">mdi-chevron-down</v-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainComponent",
};
</script>

<style scoped>
.bg {
  width: 100%;
  background-image: url("../assets/bg.png");
  background-size: cover;
  background-position: center center;
}
.content {
  margin: 0 auto;
  width: 60%;
  padding-top: 12%;
  border-bottom: 0.5rem solid red;
}
.socials{
  margin: 0 auto;
  width: 60%;
}
.name {
  font-family: TitilliumWeb-Regular;
  letter-spacing: 2rem;
  font-size: 1.2rem;
  color: white;
  text-align: center;
  margin-bottom: 3%;
}
.self {  
  font-family: TitilliumWeb-Black !important;
  color: #F5F5F5;
  text-align: center;
  font-size: 9rem;
  line-height: 7rem;
}
.self:nth-child(3){
  margin-bottom: 6%;
}
.socials{
  margin-top: 2%;
}
.icon{
  margin: 0 3%;
}
.v-icon:hover{
  transform: translateY(-4px);
  box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.2);
}
.arrow{
  animation: pulseAnimation 2s infinite;
}
.scroll{
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding-bottom: 2%;
  padding-top: 6%;
}
@keyframes pulseAnimation {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px); /* Adjust the vertical movement */
  }
}
</style>

