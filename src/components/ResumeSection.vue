<template>
  <div class="bg">
    <div class="content">
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
</template>

<script>
export default {
  name: "ResumeSection",
  methods:{
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
</style>
