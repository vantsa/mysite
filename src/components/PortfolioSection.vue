<template>
    <div class="bg">
        <div class="content">
            <h4>CHECK OUT MY PROJECTS</h4>
            <v-row justify="center">
                <v-col align="center" @click="openWL">
                    <div class="box">
                        <img src="../assets/wl.jpg">
                        <p><strong>Weekend Lake Festival</strong><br>(HTML, CSS, JS)</p>
                    </div>
                </v-col>
                <v-col align="center" @click="openLE">
                    <div class="box">
                        <img src="../assets/le.png">
                        <p><strong>Final Project</strong><br>(Vue.js, ASP .NET Core)</p>
                    </div>
                </v-col>
                <v-col align="center" @click="openWS">
                    <div class="box">
                        <img src="../assets/ws.png">
                        <p><strong>Grocery store</strong><br>(Vue.js, PHP)</p>
                    </div>
                </v-col>
            </v-row>
        </div>
    </div>
</template>

<script>

export default {
    name: 'PortfolioSection',
    methods: {
        openWL() {
            window.open("https://github.com/vantsa/Weekend-Lake-Festival-first-template")
                },
        openLE() {
            this.$router.push('https://github.com/vantsa/allamvizsga');
        },
        openWS() {
            this.$router.push('https://github.com/istiballo/webprog_frontend_final');
        }
    }
};
</script>

<style scoped>
.bg{
    width: 100%;
    background-color: #001b3b;
}
.content{
    width: 70%;
    margin: 0 auto;
}
.box{
    transition: transform 1s ease;
}
h4{
    color: white;
    font-family: Titilliumweb-Black;
    letter-spacing: 4px;
    font-size: 2.5rem;
    text-align: center;
    padding-top: 8%;
    padding-bottom: 8%;
}
img{
    width: 80%;
    margin: 0 auto;
    border-radius: 30px;
}
p{
    color: white;
    text-align: center;
    font-family: TitilliumWeb-Light;
    letter-spacing: 3.5px;
    padding: 1rem;
    font-size: 0.9rem;
}
.box:hover {
  transform: scale(1.2);
  cursor: pointer;
}
</style>