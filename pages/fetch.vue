<template>
    <information data="When we fetch data from a server in JavaScript, such as retrieving information from a database or resources like images and videos, promises handle this asynchronous task efficiently. Promises allow JavaScript to continue executing other code while waiting for the server's response. Once the data is ready, the promise is either fulfilled with the data or rejected with an error, ensuring responsive and streamlined code execution. - ChatGPT"/>
    <a-flex gap="large">
        <a-flex vertical align="center">
            <LaptopOutlined style="font-size: 200px;"/>
            <span>Client Side / Front End</span>
        </a-flex>
        <SwapOutlined style="font-size: 50px;"/>
        <a-flex vertical align="center">
            <CloudServerOutlined style="font-size: 200px;"/>
            <span>Backend</span>
        </a-flex>
    </a-flex>
    <a-flex vertical gap="large" style="margin-top: 100px;">
        
    </a-flex>
    <a-row gutter="[10,10]" style="margin-top: 100px;" align="center">
        <a-col span="6">
            <img v-if="dogImageUrl1 != ''" :src="dogImageUrl1" alt="" style="width: 300px;">
            <a-button @click="getDogPictures1">JavaScript Fetch (Then/Catch)</a-button>
        </a-col>
        <a-col span="6">
            <img v-if="dogImageUrl2 != ''" :src="dogImageUrl2" alt="" style="width: 300px;">
            <a-button @click="getDogPictures2">JavaScript Fetch (Async/Await)</a-button>
        </a-col>
        <a-col span="6">
            <img v-if="dogImageUrl3 != ''" :src="dogImageUrl3" alt="" style="width: 300px;">
            <a-button @click="getDogPictures3">Nuxt (useFetch)</a-button>
        </a-col>
        <a-col span="6">
            <img v-if="dogImageUrl4 != ''" :src="dogImageUrl4" alt="" style="width: 300px;">
            <a-button @click="getDogPictures4">3rd Party package (Axios)</a-button>
        </a-col>
    </a-row>
</template>

<script lang="ts" setup>
    import axios from 'axios';
    definePageMeta({
        layout: 'menu'
    })

    const dogImageUrl1 = ref('')
    const dogImageUrl2 = ref('')
    const dogImageUrl3 = ref('')
    const dogImageUrl4 = ref('')

    ////Using the Fetch API Then/Catch
    function getDogPictures1() {
        fetch("https://dog.ceo/api/breeds/image/random")
        .then((response) => {
            return response.json()
        })
        .then((dog) => {
            dogImageUrl1.value = dog.message
            console.log(dogImageUrl1.value)
        })
        .catch((error => {
            console.error(error)
        }))
    }

    //Using the Fetch API Async/Await
    async function getDogPictures2() {
        try {
            const response = await fetch("https://dog.ceo/api/breeds/image/random");
            const dog = await response.json();
            console.log(dog);
            dogImageUrl2.value = dog.message
        }
        catch(error) {
            console.error(error)
        }
    }

    //Using Nuxt 3 useFetch
    async function getDogPictures3() {
        try {
            const response = await useFetch("https://dog.ceo/api/breeds/image/random")
            console.log(response.data._value.message)
            dogImageUrl3.value = response.data._value.message
        }
        catch(error) {
            console.error(error)
        }
    }

    //Using Axios
    async function getDogPictures4() {
        try {
            const response = await axios.get("https://dog.ceo/api/breeds/image/random")
            dogImageUrl4.value = response.data.message
        }
        catch(error) {
            console.error(error)
        }
    }
</script>