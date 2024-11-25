<template>
    <footer class="bg-[#1B5E20] text-white py-16 border-t border-gray-800">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-8 md:mb-0">
                    <h3 class="text-2xl font-bold mb-4">Tanikan</h3>
                    <p class="text-gray-400">Revolutionizing fish farming with AI and IoT</p>
                </div>
                <div class="flex flex-col items-center md:items-end">
                    <div class="flex gap-4 mb-4">
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32] transition duration-300">
                            <Facebook class="w-6 h-6" />
                        </a>
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32] transition duration-300">
                            <Twitter class="w-6 h-6" />
                        </a>
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32] transition duration-300">
                            <Linkedin class="w-6 h-6" />
                        </a>
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32] transition duration-300">
                            <Instagram class="w-6 h-6" />
                        </a>
                    </div>
                    <p class="text-gray-400">&copy; 2024 Tanikan. All rights reserved.</p>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>
import {
    Linkedin,
    Twitter,
    Facebook,
    Instagram
} from 'lucide-vue-next'
</script>