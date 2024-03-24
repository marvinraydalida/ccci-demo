<template>
    <information data="A watcher is a feature that allows you to perform some action whenever a specific data property changes its value."/>

    <a-flex gap="large">
        <a-flex vertical>
            <img src="/wilyam.jpg" alt="wiyum" style="height: 250px;">
            <a-button @click="mayGinawangBagay">May ginawang bagay</a-button>
        </a-flex>
        <ArrowRightOutlined style="font-size: 50px;"/>
        <a-flex vertical>
            <img src="https://unboxdiaries.b-cdn.net/wp-content/uploads/2022/12/image-250.png" alt="marites" style="height: 250px;">
        </a-flex>
    </a-flex>
</template>

<script lang="ts" setup>
    definePageMeta({
        layout: 'menu'
    })

    const ganap = ref(0);

    const mayGinawangBagay = () => {
        ganap.value++;
    }

    //Marites
    watch(ganap, (value) => {
        alert(`Mga Mars alam niyo ba si wilyam ${chismis[value]}`)
    })


    const chismis = ['','nag du-drugs yan!', 'May kabit', 'Tumataba'];
</script>