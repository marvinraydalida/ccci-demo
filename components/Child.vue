<template>
    <a-flex vertical>
        Child Component
        <div id="child">
            <a-button @click="emits('decrement')">
                Child Button (Decrement)
            </a-button>
        </div>
    </a-flex>
</template>

<script setup>
    const emits = defineEmits(['decrement', 'setName'])
</script>

<style scoped>
    #child {
        padding: 10px;
        border: 1px solid red;
        border-radius: 4px;
        width: 300px;
        height: 300px;
    }
</style>