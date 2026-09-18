<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);
const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
    <nav class="fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-md border-b border-pink-100 shadow-sm">
        <div class="mx-auto max-w-7xl px-6 py-3">
            <div class="flex items-center justify-between h-16">
                <!-- Logo -->
                <a href="/" class="flex items-center gap-2.5 group">
                    <img src="/uma-logo.webp" alt="uma-logo" class="w-40" />
                </a>

                <!-- Desktop Nav Links -->
                <div class="hidden md:flex items-center gap-1">
                    <a href="/" class="nav-link active">Home</a>
                    <a href="#" class="nav-link">Characters</a>
                    <a href="#" class="nav-link">Voice Actors</a>
                    <a href="#" class="nav-link">About</a>
                </div>

                <!-- CTA Button -->
                <div class="hidden md:flex items-center gap-3">
                    <a href="#" class="px-4 py-2 text-sm font-semibold text-pink-600 hover:text-pink-700 transition-colors duration-200"> Login </a>
                    <a href="#" class="px-4 py-2 text-sm font-semibold text-white bg-gradient-to-r from-pink-500 to-rose-500 rounded-xl hover:from-pink-600 hover:to-rose-600 shadow-sm hover:shadow-md hover:shadow-pink-200 transition-all duration-200"> Sign Up </a>
                </div>

                <!-- Hamburger (Mobile) -->
                <button @click="toggleMenu" class="md:hidden flex flex-col justify-center items-center w-9 h-9 rounded-lg hover:bg-pink-50 transition-colors duration-200 gap-1.5" :aria-expanded="isMenuOpen" aria-label="Toggle menu">
                    <span class="block w-5 h-0.5 bg-gray-600 rounded-full transition-all duration-300" :class="isMenuOpen ? 'rotate-45 translate-y-2' : ''"></span>
                    <span class="block w-5 h-0.5 bg-gray-600 rounded-full transition-all duration-300" :class="isMenuOpen ? 'opacity-0 scale-x-0' : ''"></span>
                    <span class="block w-5 h-0.5 bg-gray-600 rounded-full transition-all duration-300" :class="isMenuOpen ? '-rotate-45 -translate-y-2' : ''"></span>
                </button>
            </div>

            <!-- Mobile Menu -->
            <div class="md:hidden overflow-hidden transition-all duration-300 ease-in-out" :class="isMenuOpen ? 'max-h-72 pb-4' : 'max-h-0'">
                <div class="flex flex-col gap-1 pt-2 border-t border-pink-100">
                    <a href="/" class="mobile-nav-link">Home</a>
                    <a href="#" class="mobile-nav-link">Characters</a>
                    <a href="#" class="mobile-nav-link">Voice Actors</a>
                    <a href="#" class="mobile-nav-link">About</a>
                    <div class="flex gap-2 mt-3 pt-3 border-t border-pink-100">
                        <a href="#" class="flex-1 text-center py-2 text-sm font-semibold text-pink-600 border border-pink-200 rounded-xl hover:bg-pink-50 transition-colors duration-200">Login</a>
                        <a href="#" class="flex-1 text-center py-2 text-sm font-semibold text-white bg-gradient-to-r from-pink-500 to-rose-500 rounded-xl hover:from-pink-600 hover:to-rose-600 transition-all duration-200">Sign Up</a>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- Spacer to push content below fixed navbar -->
    <div class="h-16"></div>
</template>

<style scoped>
@reference "tailwindcss";

.nav-link {
    @apply px-4 py-2 text-sm font-semibold text-gray-600 rounded-lg hover:text-pink-600  transition-all duration-200;
}

.nav-link.active {
    @apply text-pink-600 bg-pink-50;
}

.mobile-nav-link {
    @apply px-4 py-2.5 text-sm font-semibold text-gray-700 rounded-lg hover:text-pink-600 hover:bg-pink-50 transition-all duration-200;
}
</style>
