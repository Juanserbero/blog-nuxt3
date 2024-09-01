<script setup>
const route = useRoute()
const { data: posts, error, pending } = await useLazyFetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
</script>

<template>
     <div v-if="pending">
        <h1 class="text-3xl font-bold mb-10">Cargando ...</h1>
    </div>
    <div v-else-if="error || !posts">
        <h1 class="text-3xl font-bold mb-10">Ha ocurrido un error</h1>
    </div>
    <div v-else>
        <h1 class="text-3xl font-bold">{{ posts.title }}</h1>
        <p>{{ posts.body }}</p>
    </div>
</template>