<template>
    <section id="cta" class="bg-[#1B5E20] text-white py-24">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-4xl font-bold mb-6">Ready to Revolutionize Your Fish Farm?</h2>
            <p class="text-xl mb-12 text-gray-300">Join hundreds of farmers who trust Tanikan for efficient and
                sustainable
                fish farming solutions.</p>
            <div class="flex justify-center gap-6">
                <button
                    class="bg-[#2E7D32] text-white font-bold py-4 px-8 rounded-full hover:bg-[#0e4211] transition duration-300 flex items-center gap-2">
                    <ArrowRight class="w-5 h-5" />
                    Get Started
                </button>
                <button
                    class="bg-transparent border-2 border-white text-white font-bold py-4 px-8 rounded-full hover:bg-white hover:text-[#1B5E20] transition duration-300 flex items-center gap-2">
                    <Phone class="w-5 h-5" />
                    Request a Demo
                </button>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    ArrowRight,
    Phone
} from 'lucide-vue-next'
</script>