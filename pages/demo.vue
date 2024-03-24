<template>
    <!-- key: 3eae3080 -->
    <!-- https://www.omdbapi.com/ -->
    <a-flex gap="small">
        <a-input v-model:value="title" @keyup.enter="searchMovie"></a-input>
        <a-button @click="searchMovie">Search</a-button>
    </a-flex>
    <!-- <span v-if="result">{{ result.Search }}</span> -->
    <a-row v-if="result" :gutter="[10,10]" style="margin-top: 50px;">
        <a-col v-for="movie in result.Search" :key="movie.imdbID">
            <Poster :title="movie.Title" :id="movie.imdbID" :poster="movie.Poster"/>
        </a-col>
    </a-row>
</template>

<script setup>
    definePageMeta({
        layout: 'menu'
    })

    const title = ref('')
    const result = ref(null)

    const searchMovie = async () => {
        const response = await fetch(`http://www.omdbapi.com/?apikey=3eae3080&s=${title.value}`)
        console.log(response)
        const value = await response.json()
        console.log(value)
        result.value = value
        if(result.value)
        console.log(result.value.Search)
    }

</script>

