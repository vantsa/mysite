<template>
    <div class="bg">
        <div class="content">
            <v-row>
                <v-col class="center">
                    <h4>Copyright ©2023<br>All rights reserved.</h4>
                </v-col>
                <v-col align="right">
                    <h4 class="contact">Contact</h4>
                       <p><strong>Tel.:</strong> +40754 782 121</p>
                       <p><strong>Email:</strong> alparvantsa@gmail.com</p>
                </v-col>
            </v-row>
        </div>
    </div>
</template>

<script>

export default {
    name: 'FooterSection',
};
</script>

<style scoped>
.bg{
    background-color: #001b3b;

    margin-top: -1%;
}
.content{
    width: 70%;
    margin: 0 auto;
    padding: 2%;
}
h4{
    color: white;
    font-family: TitilliumWeb-Bold;
        text-align: center;
        font-size: 1.5rem;

}
.contact{
    padding-bottom: 2%;
}
.center{
    display: flex;
    flex-direction: column;
    justify-content: center;
}
p{
    color: white;
    font-family: TitilliumWeb-Regular;
    line-height: 10px;
    letter-spacing: 1px;
    text-align: center;
}
</style>
