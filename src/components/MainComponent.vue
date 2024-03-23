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
  background-image: url("../assets/bg.jpg");
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
@media screen and (max-width: 1800px){
  .name{
    margin-bottom: 5%;
  }
  .socials{
    margin-top: 5%;
  }
  .arrow{
    margin-bottom: 5%;
  }
}
@media screen and (max-width: 1400px){
  .self:nth-child(2){
    margin-bottom: 8%;
  }
  .arrow{
    margin-bottom: 3%;
  }
  .socials{
    margin-top: 5%; 
  }
}
@media screen and (max-width: 1300px)
{
  .name{
    margin-bottom: 10%;
  }
  .self{

    line-height: 5rem;
  }
.self:nth-child(2){
    margin-bottom: 10%;
  }
  .socials{
    margin-bottom: 5%;
  }
}
@media screen and (max-width: 1200px)
{
  .name{
    margin-bottom: 10%;
  }
  .self{

    line-height: 5rem;
  }
.self:nth-child(3){
    margin-bottom: 10%;
  }
  .socials{
    margin-bottom: 5%;
  }
  .arrow{
    margin-top: 5%;
  }
}
@media screen and (max-width: 1000px)
{
  .name{
    margin-bottom: 10%;
  }
  .self{

    line-height: 5rem;
  }
.self:nth-child(3){
    margin-bottom: 15%;
  }
  .socials{
    margin-top: 8%;
  }
  .arrow{
    margin-top: 5%;
  }
}
@media screen and (max-width: 900px){
  .self{
    font-size: 7.4rem;
    line-height: 4rem;
  }
  .name{
    padding-left: 5%;
    padding-top: 8%;
    padding-bottom: 6%;
  }
  .self:nth-child(3){
    margin-bottom: 20%;
  }
  .socials{
    margin-top: 8%;
  }
  .arrow{
    margin-top:2%;
    margin-bottom: 8%;
  }
}
@media screen and (max-width: 800px){
  .socials{
    margin-top:12%;
    margin-bottom: 10%;
  }
}
@media screen and (max-width: 728px){
  .self{
    font-size: 6rem;
    line-height: 5rem;
  }
  .name{
    margin-top: 10%;
    font-size: 1rem;
    letter-spacing: 1rem;
    line-height: 2rem;
  }
  .socials{
    margin-top: 13%;
  }
}
@media screen and (max-width: 600px){
  .name{
    margin-top: 1%;
    margin-bottom: 25%;
    line-height: 2.5rem;
  }
  .self{
    font-size: 4.9rem;
    line-height: 4.5rem;
  }
  .self:nth-child(3){
    margin-bottom: 30%;
  }
  .arrow{
    margin-top: 5%;
  }
  .socials{
    margin-top: 18%;
  }
}
@media screen and (max-width: 500px){
  .self{
    font-size: 4.4rem;
    line-height: 4.5rem;
  }
  .name{
    margin-top: 17%;
    padding-left: 0%;
    letter-spacing: 0.7rem;
  }
  .self:nth-child(3){
    margin-bottom: 40%;
  }
  .arrow{
    margin-bottom: 20%;
  }
}
@media screen and (max-width: 400px){
  .self{
    font-size: 3rem;
    line-height: 3rem;
  }
  .icon{
    padding: 10%;
  }
  .arrow{
    margin-top: 15%;
    margin-bottom: 25%;
  }
}
</style>

