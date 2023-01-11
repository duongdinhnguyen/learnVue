<script lang="ts" setup>
    import { reactive } from "vue";
    import axios from "axios";

    const formData = reactive({
        name: '',
        email: '',
        password: ''
    })
    const register = reactive({
        data: []
    })

    const submitRegister = async () => {
        /*
        // call api server with fetch

        await fetch('http://127.0.0.1:8000/api/auth/register', {
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json'
            },
            method: "POST",
            body: JSON.stringify(formData)
        })
        .then((response) => response.json())
        .then((data) => register.data = data)

        console.log(register.data);
        */

        // call api server with axios
        axios({
            method: "post",
            url: "http://127.0.0.1:8000/api/auth/register",
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
    <form class="form-register" @submit.prevent="submitRegister">
        <div>
            <h2>Register</h2>
        </div>
        <div>
            <div class="form-element">
                <label for="name">Tên đăng nhập</label>
                <input id="name" type="text" v-model="formData.name">
            </div>
            <div class="form-element">
                <label for="email">Email</label>
                <input id="email" type="text" v-model="formData.email">
            </div>
            <div class="form-element">
                <label for="password">Password</label>
                <input id="password" type="text" v-model="formData.password">
            </div>
            <div>
                <button>Submit</button>
            </div>
        </div>
    </form>
</template>

<style>
    .form-register {
        margin: 0 40%;
    }

    .flex {
        display: flex;
    }

    label {
        width: 180px;
    }
    .form-element {
        width: 180px
    }
</style>