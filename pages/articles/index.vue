<script setup>
const posts = await queryContent().find()
</script>

<template>
    <h1 class="text-3xl font-bold mb-10">Local Articles</h1>
    <section class="grid grid-cols-4 gap-10">
        <article
        class="hover:animate-background rounded-xl bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 p-0.5 shadow-xl transition hover:bg-[length:400%_400%] hover:shadow-sm hover:[animation-duration:_4s]"
        v-for="{ title, id, _path } in posts" :key="id"
        >
            <div class="rounded-[10px] bg-white p-4 !pt-20 sm:p-6">
                <NuxtLink :to="`/articles${_path}`">
                    <h3 class="mt-0.5 text-lg font-medium text-gray-900">
                        {{ title }} 
                    </h3>
                </NuxtLink>
            </div>
        </article>

    
    </section>
</template>