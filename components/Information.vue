<template>
    <div class="info">
        <a-row>
            <a-col span="1">
                <InfoCircleOutlined style="color: rgb(49, 202, 248);"/>
            </a-col>
            <a-col span="23">
                {{ props.data }}
            </a-col>
        </a-row>
    </div>
</template>

<script setup>
    const props = defineProps(['data'])
</script>

<style scoped>
    .info {
        border-radius: 4px;
        padding: 10px;
        background-color: rgba(49, 202, 248, 0.089);
        border: 1px solid rgb(49, 202, 248);
        margin-bottom: 20px;
        width: 900px;
    }
</style>