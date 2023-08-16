<template>
  <div class="main">
    <v-row>
      <v-col cols="6">
        <img src="../assets/lang.png" />
      </v-col>
      <v-col cols="6">
        <h3>Get in touch</h3>
        <div class="abouttext">
          <v-form @submit.prevent="submitForm">
            <v-text-field v-model="name" label="Name" required></v-text-field>
            <v-text-field v-model="email" label="Email" required></v-text-field>
            <v-textarea v-model="message" label="Message" required></v-textarea>
            <v-btn type="submit" color="primary">Send</v-btn>
          </v-form>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: "ContactSection",
  data() {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  methods: {
    async submitForm() {
        const formData = {
            name: this.name,
            email: this.email,
            message: this.message
        };

              try {
        await axios.post('https://formspree.io/alparvantsa@gmail.com', formData);
        this.name = '';
        this.email = '';
        this.message = '';
        // You can also display a success message to the user
      } catch (error) {
        // Handle errors, show error message to the user
      }
    }
  }
}
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
</style>
