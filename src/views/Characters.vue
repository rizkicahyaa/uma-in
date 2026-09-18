<script setup>
import characters from "../data/umamusume_characters.json";
import CharacterCard from "../components/CharacterCard.vue";
</script>

<template>
    <main class="min-h-screen bg-gray-100 px-6 py-12">
        <div class="mx-auto max-w-6xl">
            <!-- Header -->
            <div class="mb-10 text-center">
                <h1 class="text-4xl font-bold text-gray-900">Uma Musume Characters</h1>

                <p class="mt-3 text-gray-500">Explore characters and their voice actors.</p>
            </div>

            <!-- Character Grid -->
            <div class="grid grid-cols-1 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3">
                <CharacterCard v-for="character in characters" :key="character.url" :character="character" />
            </div>
        </div>
    </main>
</template>
