<template>
    <a-layout>
        <a-flex>
            <a-layout-sider style="height: 100vh;" width="300">
                <a-menu
                    style="height: 100vh;"
                    v-model:selectedKeys="selectedKeys"
                    mode="inline"
                    :items="items"
                    @click="handleClick"
                />
            </a-layout-sider>
            <a-layout-content style="padding: 50px;">
                <slot />
            </a-layout-content>
        </a-flex>
        
    </a-layout>
</template>

<script lang="ts" setup>
    import { h, ref } from 'vue';
    import type { CSSProperties } from 'vue';
    import {
        RocketOutlined,
        EyeOutlined,
        NodeExpandOutlined,
        CloudSyncOutlined,
        PlaySquareOutlined
    } from '@ant-design/icons-vue';
    import type { MenuProps } from 'ant-design-vue';
    const selectedKeys = ref(['emits']);

    const items = ref([
        {
            key: 'emits',
            icon: () => h(RocketOutlined),
            label: 'Emits',
            title: 'emits',
        },
        {
            key: 'watcher',
            icon: () => h(EyeOutlined),
            label: 'Watcher',
            title: 'watcher',
        },
        {
            key: 'async',
            icon: () => h(NodeExpandOutlined),
            label: 'Promise',
            title: 'async',
        },
        {
            key: 'fetch',
            icon: () => h(CloudSyncOutlined),
            label: 'Data Fetching',
            title: 'fetch',
        },
        {
            key: 'demo',
            icon: () => h(PlaySquareOutlined),
            label: 'Demo',
            title: 'Demo',
        },
    ]);

    const handleClick: MenuProps['onClick'] = e => {
        console.log('click', e);
        navigateTo(`/${e.key}`);
    };
</script>