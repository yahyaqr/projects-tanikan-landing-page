<template>
    <section class="relative bg-gradient-to-b from-[#1B5E20] to-[#2E7D32] text-white pt-32 pb-24 overflow-hidden">
        <div class="absolute inset-0 z-0 flex items-center justify-center">
            <Placeholder height="800" width="1920" background="none" alt="" class="object-cover opacity-20" />
        </div>
        <div class="container mx-auto px-4 relative z-10">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h1 class="text-6xl font-bold mb-6 leading-tight">Fish Farming for Everyone</h1>
                    <p class="text-xl mb-8 text-gray-300">Enhancing aquaculture with AI, IoT, and real-time monitoring
                        to make
                        fish farming easier, safer, and more productive.</p>
                    <button
                        class="bg-[#2E7D32] text-white font-bold py-3 px-8 rounded-full hover:bg-[#1B5E20] transition duration-300 flex items-center gap-2">
                        <ArrowRight class="w-5 h-5" />
                        Get Started
                    </button>
                </div>
                <div class="relative">
                    <Placeholder height="600" width="800" alt="Fish farming technology" class="rounded-lg shadow-2xl" />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ArrowRight } from 'lucide-vue-next'
import Placeholder from '../../assets/PlaceholderFull.vue'
</script>