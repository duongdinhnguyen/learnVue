<script lang="ts" setup>
    import { reactive } from "vue";
    import axios from "axios";

    const formData = reactive({
        email: '',
        password: ''
    })

    const handleSubmitLogin = () => {
        axios({
            method: "post",
            url: "http://127.0.0.1:8000/api/auth/login",
            data: formData,
            headers: { "Content-Type": "multipart/form-data" },
            })
        .then(function (response) {
            //handle success
            console.log(response.data);
        })
        .catch(function (response) {
            //handle error
            console.log(response);
        });
    }
</script>
<template>
    <div>
        <h2>Login</h2>
    </div>
    <form action="" @submit.prevent="handleSubmitLogin">
        <div>
        <div>
            <label for="email">Email</label>
            <input id="email" type="text" v-model="formData.email">
        </div>
        <div>
            <label for="password">Password</label>
            <input id="password" type="text" v-model="formData.password">
        </div>
        <div>
            <button type="submit">Login</button>
        </div>
    </div>
    </form>
</template>

<style>
    
</style>