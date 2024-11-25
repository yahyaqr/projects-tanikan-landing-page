<template>
    <section id="testimonials" class="bg-[#F9FAFB] text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold mb-16 text-center">What Farmers Are Saying</h2>
            <div class="grid md:grid-cols-2 gap-8">
                <div v-for="(testimonial, index) in testimonials" :key="index"
                    class="bg-white p-8 rounded-2xl shadow-lg">
                    <Quote class="w-12 h-12 text-[#2E7D32] mb-6" />
                    <p class="text-lg italic mb-6">{{ testimonial.quote }}</p>
                    <div class="flex items-center gap-4">
                        <Placeholder height="64" width="64" text="" :alt="testimonial.author" class="rounded-full" />
                        <div>
                            <p class="font-bold">{{ testimonial.author }}</p>
                            <p class="text-gray-600">{{ testimonial.role }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Quote } from 'lucide-vue-next'
import Placeholder from '../../assets/Placeholder.vue'

const testimonials = [
    {
        quote: 'Since adopting Tanikan, our productivity has increased dramatically. The Smart Alarm is a game-changer!',
        author: 'John Doe',
        role: 'Fish Farm Owner'
    },
    {
        quote: 'Tanikan\'s monitoring system has saved us both time and money, making our fish farming operations far easier to manage.',
        author: 'Jane Smith',
        role: 'Aquaculture Manager'
    },
]
</script>