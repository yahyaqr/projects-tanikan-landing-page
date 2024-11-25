<template>
    <section id="technology" class="bg-white text-[#1B5E20] py-24">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h2 class="text-4xl font-bold mb-6">AI & IoT for Smarter Aquaculture</h2>
                    <p class="text-lg leading-relaxed mb-8">
                        Our system integrates advanced IoT sensors and AI-driven analytics to monitor and control
                        critical factors
                        such as oxygen levels, feeding schedules, and water quality, ensuring a consistently healthy
                        environment
                        for your fish.
                    </p>
                    <div class="flex gap-4">
                        <div class="flex items-center gap-2">
                            <Cpu class="w-6 h-6 text-[#2E7D32]" />
                            <span>AI-Powered</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <Wifi class="w-6 h-6 text-[#2E7D32]" />
                            <span>IoT Enabled</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <Shield class="w-6 h-6 text-[#2E7D32]" />
                            <span>Secure</span>
                        </div>
                    </div>
                </div>
                <Placeholder height="400" width="600" alt="Technology overview" class="rounded-lg shadow-xl" />
            </div>
        </div>
    </section>

</template>

<script setup>
import { Cpu, Wifi, Shield } from 'lucide-vue-next'
import Placeholder from '../../assets/PlaceholderFull.vue'
</script>