<template>
    <section id="how-it-works" class="bg-[#E5F4F3] text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">How Tanikan Transforms Fish Farming</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div v-for="(step, index) in howItWorks" :key="index" class="relative">
                    <div class="bg-white rounded-2xl p-8 h-full shadow-lg">
                        <div
                            class="bg-[#2E7D32] text-white rounded-full w-12 h-12 flex items-center justify-center text-xl font-bold mb-6">
                            {{ index + 1 }}
                        </div>
                        <component :is="step.icon" class="w-8 h-8 text-[#2E7D32] mb-4" />
                        <h3 class="text-xl font-bold mb-4">{{ step.title }}</h3>
                        <p class="text-gray-700">{{ step.description }}</p>
                    </div>
                    <div v-if="index < 3"
                        class="hidden lg:block absolute top-1/2 left-full w-8 h-0.5 bg-[#2E7D32] -translate-y-1/2">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    Upload,
    Activity,
    Database,
    BarChart
} from 'lucide-vue-next'

const howItWorks = [
    {
        title: 'Install IoT Devices',
        description: 'Easily set up Tanikan\'s IoT devices across ponds and fish tanks.',
        icon: Upload
    },
    {
        title: 'Real-Time Monitoring',
        description: 'Track fish activity, water quality, and aeration through the app.',
        icon: Activity
    },
    {
        title: 'AI-Powered Alerts',
        description: 'Receive immediate notifications and recommendations to keep conditions optimal.',
        icon: Database
    },
    {
        title: 'Analytics & Insights',
        description: 'Data-driven insights to help make informed decisions, reduce risks, and boost productivity.',
        icon: BarChart
    },
]
</script>