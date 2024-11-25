<template>
    <section id="benefits" class="bg-[#1B5E20] text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center text-white">Why Choose Tanikan?</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div v-for="(benefit, index) in benefits" :key="index"
                    class="bg-[#AED581] p-8 rounded-2xl hover:bg-[#C5E1A5] transition duration-300">
                    <component :is="benefit.icon" class="w-12 h-12 text-[#2E7D32] mb-6" />
                    <h3 class="text-xl font-bold mb-4">{{ benefit.title }}</h3>
                    <p class="text-gray-700">{{ benefit.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    Leaf,
    Scale,
    DollarSign,
    TrendingUp
} from 'lucide-vue-next'

const benefits = [
    {
        title: 'Sustainability',
        description: 'Minimize resource waste with precise monitoring.',
        icon: Leaf
    },
    {
        title: 'Scalability',
        description: 'Ideal for fish farms of any size, from small to large.',
        icon: Scale
    },
    {
        title: 'Cost Efficiency',
        description: 'Lower labor and resource expenses with intelligent automation.',
        icon: DollarSign
    },
    {
        title: 'Increased Productivity',
        description: 'Healthier fish populations lead to higher yields.',
        icon: TrendingUp
    },
]
</script>