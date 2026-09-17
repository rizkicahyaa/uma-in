<script setup>
defineProps({
    character: {
        type: Object,
        required: true,
    },
});
</script>

<template>
    <div class="overflow-hidden rounded-2xl bg-white shadow-md transition duration-300 hover:-translate-y-1 hover:shadow-xl">
        <!-- Character Image -->
        <img :src="character.image" :alt="character.name" class="h-72 w-full object-cover" />

        <!-- Content -->
        <div class="p-5">
            <h2 class="text-xl font-bold text-gray-900">
                {{ character.name }}
            </h2>

            <p class="mt-2 text-sm text-gray-500">Voiced by</p>

            <p class="font-medium text-gray-800">
                {{ character.voice_actor || "Unknown" }}
            </p>

            <a :href="character.url" target="_blank" rel="noopener noreferrer" class="mt-4 inline-block rounded-lg bg-pink-500 px-4 py-2 text-sm font-semibold text-white transition hover:bg-pink-600"> View Details </a>
        </div>
    </div>
</template>
