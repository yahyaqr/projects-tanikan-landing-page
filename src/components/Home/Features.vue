<template>
    <section id="features" class="bg-white text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">Key Features</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div v-for="(feature, index) in features" :key="index" :class="feature.bgColor"
                    class="p-8 rounded-2xl transition-transform hover:scale-105 duration-300 hover:shadow-lg">
                    <component :is="feature.icon" class="w-12 h-12 text-[#2E7D32] mb-6" />
                    <h3 class="text-2xl font-bold mb-4">{{ feature.title }}</h3>
                    <p class="text-gray-700">{{ feature.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    Camera,
    Bell,
    Wind,
    Smartphone
} from 'lucide-vue-next'

const features = [
    {
        title: 'FishCam',
        description: 'Real-time video monitoring and insights on fish health and activity.',
        bgColor: 'bg-[#F1F8E9]',
        icon: Camera
    },
    {
        title: 'Smart Alarm',
        description: '24/7 alerts and emergency notifications to ensure optimal conditions.',
        bgColor: 'bg-[#DCEDC8]',
        icon: Bell
    },
    {
        title: 'Aeration Control',
        description: 'Automate and monitor oxygen levels for ideal water conditions.',
        bgColor: 'bg-[#C5E1A5]',
        icon: Wind
    },
    {
        title: 'Mobile App',
        description: 'Manage your fish farm remotely with ease through our intuitive app.',
        bgColor: 'bg-[#AED581]',
        icon: Smartphone
    },
]
</script>