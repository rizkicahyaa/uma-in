<script setup>
defineProps({
    character: {
        type: Object,
        required: true,
    },
});
</script>

<template>
    <div class="overflow-hidden rounded-2xl bg-white shadow-md transition-shadow duration-300 hover:shadow-xl">
        <!-- Images -->
        <div class="grid grid-cols-2 gap-1 bg-gray-100">
            <!-- Character Image -->
            <div class="relative overflow-hidden">
                <img :src="character.image" :alt="character.name" referrerpolicy="no-referrer" class="h-50 w-100 object-cover" />

                <span class="absolute bottom-2 left-2 rounded-md bg-black/60 px-2 py-1 text-xs font-medium text-white backdrop-blur-sm"> Character </span>
            </div>

            <!-- Voice Actor Image -->
            <div class="relative overflow-hidden">
                <img :src="character.voice_actor_image" :alt="character.voice_actor" referrerpolicy="no-referrer" class="h-50 w-full object-cover" />

                <span class="absolute bottom-2 left-2 rounded-md bg-black/60 px-2 py-1 text-xs font-medium text-white backdrop-blur-sm"> Voice Actor </span>
            </div>
        </div>

        <!-- Content -->
        <div class="p-5">
            <h2 class="text-xl font-bold leading-tight text-gray-900">
                {{ character.name }}
            </h2>

            <div class="mt-3">
                <p class="text-xs font-medium uppercase tracking-wider text-gray-400">Voiced by</p>

                <p class="mt-1 font-semibold text-gray-800">
                    {{ character.voice_actor || "Unknown" }}
                </p>
            </div>

            <a :href="character.url" target="_blank" rel="noopener noreferrer" class="mt-5 inline-flex w-full items-center justify-center rounded-lg bg-pink-500 px-4 py-2.5 text-sm font-semibold text-white transition-colors duration-200 hover:bg-pink-600"> View Details </a>
        </div>
    </div>
</template>
