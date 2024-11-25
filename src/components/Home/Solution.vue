<template>
    <section id="solution" class="bg-white text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-12">
                <div class="bg-[#FAF2F0] p-8 rounded-2xl">
                    <AlertTriangle class="w-12 h-12 text-red-500 mb-6" />
                    <h3 class="text-3xl font-bold mb-6">The Problem</h3>
                    <ul class="space-y-4">
                        <li class="flex items-start gap-3">
                            <XCircle class="w-6 h-6 text-red-500 flex-shrink-0 mt-1" />
                            <span>Labor-intensive practices requiring constant manual oversight</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <XCircle class="w-6 h-6 text-red-500 flex-shrink-0 mt-1" />
                            <span>High risk of fish mortality without real-time monitoring</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <XCircle class="w-6 h-6 text-red-500 flex-shrink-0 mt-1" />
                            <span>Resource inefficiency leading to increased costs</span>
                        </li>
                    </ul>
                </div>
                <div class="bg-[#F0FBFA] p-8 rounded-2xl">
                    <Lightbulb class="w-12 h-12 text-[#2E7D32] mb-6" />
                    <h3 class="text-3xl font-bold mb-6">Our Solution</h3>
                    <p class="text-lg mb-6">
                        Tanikan combines IoT, AI, and data analytics to automate monitoring and management, reducing
                        labor and
                        optimizing conditions in real-time.
                    </p>
                    <Placeholder height="300" width="500" alt="Tanikan solution" class="rounded-lg" />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import {
    AlertTriangle,
    XCircle,
    Lightbulb
} from 'lucide-vue-next'
import Placeholder from '../../assets/PlaceholderFull.vue'
</script>