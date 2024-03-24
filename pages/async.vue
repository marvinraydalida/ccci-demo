<template>
    <Information data="Promises are meant to be broken :'("/>
    <Information data="A JavaScript promise is like ordering a pizza: you make a request (promise) to get something (pizza) in the future. While you wait, the promise is in a pending state. When the pizza arrives successfully, it's like the promise being resolved, and if there's an issue with delivery, it's like the promise being rejected."/>
</template>

<script lang="ts" setup>
    definePageMeta({
        layout: 'menu'
    })

    // Creating a promise for a fake pizza delivery
    const pizzaDelivery = new Promise((resolve, reject) => {
    // Simulate pizza delivery taking some time
        setTimeout(() => {
            const delivered = false; // Pretend the pizza was delivered successfully
            if (delivered) {
                resolve("Delicious pizza!"); // Resolve the promise with the result
            } else {
                reject("Oops! Pizza delivery failed."); // Reject the promise with an error
            }
        }, 2000); // Delivery time: 2 seconds
    });

    // Using the promise with then catch
    // pizzaDelivery.then((result) => {
    //     console.log(result); // Output: Delicious pizza!
    // }).catch((error) => {
    //     console.error(error); // Output: Oops! Pizza delivery failed.
    // });


    //Using promise with async await
    // try {
    //     const result = await pizzaDelivery
    //     console.log(result)
    // }
    // catch(error) {
    //     console.error(error)
    // }
</script>