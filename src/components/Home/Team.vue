<template>
    <section id="team" class="bg-white text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">Meet the Experts Behind Tanikan</h2>
            <div class="grid md:grid-cols-3 gap-12">
                <div v-for="(member, index) in team" :key="index" class="text-center group">
                    <div class="relative mb-6 inline-block">
                        <Placeholder height="300" width="300" :alt="member.name"
                            class="w-48 h-48 rounded-full mx-auto object-cover transition duration-300 group-hover:scale-105" />
                        <div
                            class="absolute inset-0 rounded-full bg-[#2E7D32] opacity-0 group-hover:opacity-20 transition duration-300">
                        </div>
                    </div>
                    <h3 class="text-2xl font-bold mb-2">{{ member.name }}</h3>
                    <p class="text-[#2E7D32] mb-4">{{ member.role }}</p>
                    <div class="flex justify-center gap-4">
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32]">
                            <Linkedin class="w-5 h-5" />
                        </a>
                        <a href="#" class="text-gray-400 hover:text-[#2E7D32]">
                            <Twitter class="w-5 h-5" />
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    Linkedin,
    Twitter,
} from 'lucide-vue-next'
import Placeholder from '../../assets/PlaceholderFull.vue'

const team = [
    {
        name: 'Alice Johnson',
        role: 'CEO',
    },
    {
        name: 'Bob Williams',
        role: 'CTO',
    },
    {
        name: 'Carol Davis',
        role: 'Aquaculture Specialist',
    },
]
</script>