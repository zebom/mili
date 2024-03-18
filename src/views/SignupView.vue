<!-- its composition api  ...setup... -->
<script setup>
import { ref } from "vue";
import axios from "axios";


const Username = ref('')
const email = ref('')
const password = ref('')

const signup = async () => {
    console.log(`${Username.value} ${email.value} ${password.value}`);
    try {
        const response = await axios.post('http://localhost:4000/user',{
            username: Username.value,
            email: email.value,
            password: password.value
        });
        console.log(response.data); // Log response data if needed
    } catch (error) {
        console.error(error); // Log any errors
    }
    // save the values to the database
    // await axios.post('url' values)
}

</script>
<link rel="manifest" href="manifest.json">
<template>
<div class="container">
    <h1>Signup Here</h1>
    <form @submit.prevent="signup">

        <div class="sign-form">
        <div class="form-group">
            <input class="form-input" type="text" placeholder="Enter Username" v-model="Username">
        </div>
        <div class="form-group">
            <input class="form-input" type="email" placeholder="Enter Email" v-model="email">
        </div>
        <div class="form-group">
            <input class="form-input" type="password" placeholder="Enter Password" v-model="password">
        </div>
        <div class="form-group">
            <input class="form-input" type="Submit" value="Signup">
        </div>

    </div>
    </form>
    <p>{{ Username }}</p>


</div>

</template>
<!-- you write scoped if you want the style to be only this component -->
<style scoped>
.sign-form{
    background-color: rgb(191 191 220);
    width: 50%;
    border-radius: 10px;
    padding: 2% 1%; 

}
.sign-form .form-group{
    margin-bottom: 1%;
}
.sign-form .form-input{
border-style: none;
padding-top: 5px 28px;
}
</style>