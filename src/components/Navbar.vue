<template>
    <nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
        :class="{ 'bg-white shadow-md': isNavbarVisible, 'bg-transparent': !isNavbarVisible }">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center h-16">
                <a href="#" class="text-2xl font-bold"
                    :class="{ 'text-[#1B5E20]': isNavbarVisible, 'text-white': !isNavbarVisible }">Tanikan</a>
                <div class="relative">
                    <button @click="toggleDropdown" class="flex items-center space-x-2 focus:outline-none"
                        :class="{ 'text-[#1B5E20]': isNavbarVisible, 'text-white': !isNavbarVisible }">
                        <span class="sr-only">Open navigation menu</span>
                        <ChevronDown v-if="!isDropdownOpen" class="w-6 h-6" />
                        <X v-else class="w-6 h-6" />
                    </button>
                    <div v-if="isDropdownOpen"
                        class="absolute right-0 mt-2 py-2 w-48 bg-white rounded-md shadow-xl z-20">
                        <a v-for="item in navItems" :key="item.href" :href="item.href" @click="closeDropdown"
                            class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
                            {{ item.name }}
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import {
    ChevronDown,
    X
} from 'lucide-vue-next'

const isNavbarVisible = ref(false)
const isDropdownOpen = ref(false)

const navItems = [
    { name: 'Vision', href: '#vision' },
    { name: 'Solution', href: '#solution' },
    { name: 'Features', href: '#features' },
    { name: 'How It Works', href: '#how-it-works' },
    { name: 'Benefits', href: '#benefits' },
    { name: 'Technology', href: '#technology' },
    { name: 'Testimonials', href: '#testimonials' },
    { name: 'Team', href: '#team' },
]

const handleScroll = () => {
    isNavbarVisible.value = window.scrollY > 50
}

const toggleDropdown = () => {
    isDropdownOpen.value = !isDropdownOpen.value
}

const closeDropdown = () => {
    isDropdownOpen.value = false
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})
</script>