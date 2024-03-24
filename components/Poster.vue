<template>
   <a-card hoverable style="width: 240px">
    <template #cover>
      <img alt="example" :src="props.poster" style="max-height: 300px;"/>
    </template>
    <a-card-meta :title="props.title">
      <template #description>imdbID: {{ props.id }}</template>
    </a-card-meta>
  </a-card>
</template>

<script setup>
    const props = defineProps(['title', 'poster', 'id'])
</script>