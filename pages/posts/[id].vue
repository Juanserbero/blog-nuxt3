<script setup>
const route = useRoute()
const { data: posts } = await useFetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
</script>

<template>
    <h1 class="text-3xl font-bold">{{ posts.title }}</h1>
    <p>{{ posts.body }}</p>
</template>