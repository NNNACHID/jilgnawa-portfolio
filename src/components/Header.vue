<template>
    <header class="bg-gradient-to-r from-pink-100 to-purple-100 sticky top-0 z-50">
        <div class="max-w-screen-x1 mx-auto px-4 py-4 flex justify-between items-center">
            <!-- LOGO -->
            <a href="/" class="flex items-center focus:outline-none focus:ring-2 focus:ring-ping-600 rounded">
                <h1 class="text-2xl font-bold text-pink-600">Jil Gnawa</h1>
            </a>
            <!-- NAV -->
            <nav class="hidden md:flex space-x-6" aria-label="Primary navigation">
                <a v-for="(link, index) in navLinks" :key="index" :href="link.href" class="text-gray-700 hover:text-pink-600 transition-colors duration-200 focus:outline-none
                focus:ring-2 focus:ring-pink-600 rounded">{{ label }}</a>
            </nav>
            <!-- CONTACT BUTTON -->
            <div class="hidden md:block">
                <a href="#contact"
                    class="bg-pink-600 hover:bg-pink-700 text-white px-5 py-2 rounded-full transition-colors duration-200 shadow-md focus:outline-none focus:ring-2 focus:ring-pink-800 focus:ring-offset-2">Contact</a>
            </div>

            <!-- MOBILE BUTTON -->
            <button class="md:hidden p-2 focus:outline-none focus:ring-2 focus:ring-pink-600 rounded"
                @click="toggleMenu" aria-label="Toggle menu" :aria-expanded="isMenuOpen.toString()"
                aria-controls="mobile-menu">
                <Icon :icon="isMenuOpen ? 'mdi:close' : 'mdi:menu'" class="w-6 h-6" />
            </button>
        </div>

        <!-- MOBILE MENU -->
        <aside v-if="isMenuOpen" id="mobile-menu"
            class="md:hidden bg-white shadow-lg py-4 px-4 absolute top-full left-0 right-0 z-40"
            aria-label="Mobile menu">
            <nav aria-label="Mobile Navigation">
                <ul class="flex flex-col space-y-4">
                    <li v-for="(link, index) in navlinks" :key="index">
                        <a :href="link.href" class="block text-gray-700 hover:text-pink-600 transition-colors duration-200 py-2 px-2 focus:outline-none
                focus:ring-2 focus:ring-pink-600 rounded" @click="toggleMenu">
                        {{ link.label }}
                        </a>
                    </li>
                    <li>
                        
                    </li>
                </ul>
            </nav>
        </aside>
    </header>
</template>
<script>
import { ref } from 'vue';

const navLinks = ref([
    { href: '#home', label: 'Home' },
    { href: '#about', label: 'About' },
    { href: '#musics', label: 'Musics' },
    { href: '#contact', label: 'Contact' },
]);

const isMenuOpen = ref(false)
const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
}

</script>