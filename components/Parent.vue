<template>
    <information data="In Vue.js, the emits option is used in Vue components to explicitly declare custom events that the component can emit to its parent components."/>
    Parent Component
    <div id="parent">
        <a-flex vertical gap="large">
            <span>Current Value: {{ data }}</span>
            <span></span>
            <a-button @click="incrementCallback">
                Parent Button (Increment)
            </a-button>
            <Child @decrement="decrementCallback"/>
        </a-flex>
    </div>
</template>

<script setup>
    const data = ref(0);

    const incrementCallback = () => {
        data.value++
    }

    const decrementCallback = () => {
        data.value--
    }
</script>

<style scoped>
    #parent {
        padding: 10px;
        border: 1px solid green;
        border-radius: 4px;
        width:500px;
        height: 500px;
    }
</style>