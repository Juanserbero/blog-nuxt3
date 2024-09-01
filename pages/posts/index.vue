<script setup>
const { data: posts, error, pending } = await useLazyFetch('https://jsonplaceholder.typicode.com/posts')
</script>

<template>
    <div v-if="pending">
        <h1 class="text-3xl font-bold mb-10">Cargando ...</h1>
    </div>
    <div v-else-if="error || !posts">
        <h1 class="text-3xl font-bold mb-10">Ha ocurrido un error</h1>
    </div>
    
    <div v-else class="grid grid-cols-4 gap-10">
        <article
        class="hover:animate-background rounded-xl bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 p-0.5 shadow-xl transition hover:bg-[length:400%_400%] hover:shadow-sm hover:[animation-duration:_4s]"
        v-for="{ title, id } in posts" :key="id"
        >
            <div class="rounded-[10px] bg-white p-4 !pt-20 sm:p-6">
                <NuxtLink :to="`/posts/${id}`">
                    <h3 class="mt-0.5 text-lg font-medium text-gray-900">
                        {{ title }} 
                    </h3>
                </NuxtLink>
            </div>
        </article>
    </div>
</template>