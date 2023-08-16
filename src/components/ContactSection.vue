<template>
  <div class="main">
    <v-row>
      <v-col cols="6">
        <img src="../assets/lang.png" />
      </v-col>
      <v-col cols="6">
        <div class="slide-in-container" ref="slideInContainer">
          <h3>Get in touch</h3>
          <div class="abouttext">
            <v-card elevation="24">
              <v-form @submit.prevent="submitForm">
                <v-text-field
                  v-model="name"
                  label="Name"
                  :rules="nameRules"
                  required
                ></v-text-field>
                <v-text-field
                  v-model="email"
                  label="Email"
                  :rules="emailRules"
                  required
                ></v-text-field>
                <v-textarea
                  v-model="message"
                  label="Message"
                  :rules="messageRules"
                  required
                ></v-textarea>
                <v-btn
                  elevation="2"
                  rounded
                  x-large
                  color="#001b3b"
                  class="resume"
                  type="submit"
                  >Send</v-btn
                >
              </v-form>
            </v-card>
            <h4>OR VIA</h4>
            <v-row justify="center">
              <v-col class="icon" cols="auto">
                <a
                  href="https://www.linkedin.com/in/v%C3%A1ntsa-alp%C3%A1r-a6705a1b3/"
                  target="_blank"
                  ><v-icon size="4rem" color="#001b3b">mdi-linkedin</v-icon></a
                >
              </v-col>
            </v-row>
          </div>
        </div>
      </v-col>
    </v-row>
    <v-alert
      fixed
      class="alert"
      type="error"
      v-if="errorMsg"
      dismissible
      @input="errorMsg = ''"
      >{{ errorMsg }}</v-alert
    >
    <v-alert
      fixed
      class="alert"
      type="success"
      v-if="successMsg"
      dismissible
      @input="successMsg = ''"
      >{{ successMsg }}</v-alert
    >
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "ContactSection",
  data() {
    return {
      name: "",
      email: "",
      message: "",
      errorMsg: "",
      successMsg: "",
      nameRules: [(v) => !!v || "Name is required"],
      emailRules: [
        (v) => !!v || "Email is required",
        (v) => /.+@.+\..+/.test(v) || "Email must be valid",
      ],
      messageRules: [(v) => !!v || "Message is required"],
    };
  },
  methods: {
    async submitForm() {
      const formData = {
        name: this.name,
        email: this.email,
        message: this.message,
      };

      try {
        await axios.post("https://formspree.io/f/mvojkydp", formData);
        this.name = "";
        this.email = "";
        this.message = "";
        this.successMsg = "Thanks for your email!";
        this.errorMsg = "";
      } catch (error) {
        this.errorMsg = "Unknown error, please try again later.";
        this.successMsg = "";
      }
    },
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
  },
  mounted() {
    window.addEventListener("scroll", this.checkSlide);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.checkSlide);
  },
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
  padding: 5%;
  color: #001b3b;
}
.abouttext {
  width: 70%;
  margin: 0 auto;
}
img {
  width: 100%;
  box-shadow: 20px 0px 65px 0px rgba(0, 0, 0, 0.74);
}
p {
  text-align: justify;
  margin-top: -2%;
  line-height: 1.8rem;
  font-family: TitilliumWeb-Regular;
  font-weight: 600;
  font-size: 1.1rem;
  letter-spacing: 1px;
  color: #001b3b;
}
.resume {
  font-size: 1.3rem;
  text-decoration: none;
  font-family: "TitilliumWeb-Bold";
  width: 30%;
  letter-spacing: 3px;
  color: white;
  float: right;
  margin-top: 2rem;
}
.v-form {
  font-family: TitilliumWeb-Bold;
  padding: 2rem;
  padding-bottom: 7rem;
}
.v-btn:hover {
  transform: translateY(-4px);
  box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.2);
}
h4 {
  color: #001b3b;
  font-family: TitilliumWeb-Black;
  padding-top: 15%;
  text-align: center;
  font-size: 2rem;
  letter-spacing: 3px;
}
.icon {
  padding: 5%;
}
.v-icon:hover {
  transform: translateY(-4px);
  box-shadow: 0px 15px 20px rgba(0, 0, 0, 0.2);
}
.alert {
  position: fixed;
  top: 5%;
  left: 80%;
  transform: translateX(-50%);
  z-index: 9999;
  width: 40%;
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
