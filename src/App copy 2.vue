<template>
  <div class="font-sans">
    <!-- Revised Navbar -->
    <nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
      :class="{ 'bg-white shadow-md': isNavbarVisible, 'bg-transparent': !isNavbarVisible }">
      <div class="container mx-auto px-4">
        <div class="flex justify-between items-center h-16">
          <a href="#" class="text-2xl font-bold"
            :class="{ 'text-[#1B5E20]': isNavbarVisible, 'text-white': !isNavbarVisible }">Tanikan</a>
          <div class="relative">
            <button @click="toggleDropdown" class="flex items-center space-x-2 focus:outline-none"
              :class="{ 'text-[#1B5E20]': isNavbarVisible, 'text-white': !isNavbarVisible }">
              <span class="sr-only">Open navigation menu</span>
              <ChevronDown v-if="!isDropdownOpen" class="w-6 h-6" />
              <X v-else class="w-6 h-6" />
            </button>
            <div v-if="isDropdownOpen" class="absolute right-0 mt-2 py-2 w-48 bg-white rounded-md shadow-xl z-20">
              <a v-for="item in navItems" :key="item.href" :href="item.href" @click="closeDropdown"
                class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">
                {{ item.name }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative bg-gradient-to-b from-[#1B5E20] to-[#2E7D32] text-white pt-32 pb-24 overflow-hidden">
      <div class="absolute inset-0 z-0">
        <img src="/placeholder.svg?height=800&width=1920" alt="" class="w-full h-full object-cover opacity-20" />
      </div>
      <div class="container mx-auto px-4 relative z-10">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h1 class="text-6xl font-bold mb-6 leading-tight">Fish Farming for Everyone</h1>
            <p class="text-xl mb-8 text-gray-300">Enhancing aquaculture with AI, IoT, and real-time monitoring to make
              fish farming easier, safer, and more productive.</p>
            <button
              class="bg-[#2E7D32] text-white font-bold py-3 px-8 rounded-full hover:bg-[#1B5E20] transition duration-300 flex items-center gap-2">
              <ArrowRight class="w-5 h-5" />
              Get Started
            </button>
          </div>
          <div class="relative">
            <img src="/placeholder.svg?height=600&width=800" alt="Fish farming technology"
              class="rounded-lg shadow-2xl" />
          </div>
        </div>
      </div>
    </section>

    <!-- Vision Section -->
    <section id="vision" class="bg-[#E5F4F3] text-[#1B5E20] py-24">
      <div class="container mx-auto px-4">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <img src="/placeholder.svg?height=500&width=700" alt="Our vision" class="rounded-lg shadow-lg" />
          <div>
            <h2 class="text-4xl font-bold mb-6">Revolutionizing Aquaculture for All Farmers</h2>
            <p class="text-lg leading-relaxed">
              At Tanikan, we believe in accessible fish farming. By combining IoT and AI, we provide sustainable and
              efficient solutions for farmers everywhere, from individual small farms to large-scale operations. Our
              technology reduces labor, minimizes risk, and increases fish yield.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Problem & Solution Section -->
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
              Tanikan combines IoT, AI, and data analytics to automate monitoring and management, reducing labor and
              optimizing conditions in real-time.
            </p>
            <img src="/placeholder.svg?height=300&width=500" alt="Tanikan solution" class="rounded-lg" />
          </div>
        </div>
      </div>
    </section>

    <!-- Key Features Section -->
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

    <!-- How It Works Section -->
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
              class="hidden lg:block absolute top-1/2 left-full w-8 h-0.5 bg-[#2E7D32] -translate-y-1/2"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Benefits Section -->
    <section id="benefits" class="bg-[#1B5E20] text-white py-24">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl font-bold mb-16 text-center">Why Choose Tanikan?</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(benefit, index) in benefits" :key="index"
            class="bg-[#243640] p-8 rounded-2xl hover:bg-[#2D424D] transition duration-300">
            <component :is="benefit.icon" class="w-12 h-12 text-[#2E7D32] mb-6" />
            <h3 class="text-xl font-bold mb-4">{{ benefit.title }}</h3>
            <p class="text-gray-400">{{ benefit.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Technology Section -->
    <section id="technology" class="bg-white text-[#1B5E20] py-24">
      <div class="container mx-auto px-4">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-4xl font-bold mb-6">AI & IoT for Smarter Aquaculture</h2>
            <p class="text-lg leading-relaxed mb-8">
              Our system integrates advanced IoT sensors and AI-driven analytics to monitor and control critical factors
              such as oxygen levels, feeding schedules, and water quality, ensuring a consistently healthy environment
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
          <img src="/placeholder.svg?height=400&width=600" alt="Technology overview" class="rounded-lg shadow-xl" />
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="bg-[#F9FAFB] text-[#1B5E20] py-24">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl font-bold mb-16 text-center">What Farmers Are Saying</h2>
        <div class="grid md:grid-cols-2 gap-8">
          <div v-for="(testimonial, index) in testimonials" :key="index" class="bg-white p-8 rounded-2xl shadow-lg">
            <Quote class="w-12 h-12 text-[#2E7D32] mb-6" />
            <p class="text-lg italic mb-6">{{ testimonial.quote }}</p>
            <div class="flex items-center gap-4">
              <img :src="`/placeholder.svg?height=64&width=64`" :alt="testimonial.author"
                class="w-16 h-16 rounded-full" />
              <div>
                <p class="font-bold">{{ testimonial.author }}</p>
                <p class="text-gray-600">{{ testimonial.role }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section id="team" class="bg-white text-[#1B5E20] py-24">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl font-bold mb-16 text-center">Meet the Experts Behind Tanikan</h2>
        <div class="grid md:grid-cols-3 gap-12">
          <div v-for="(member, index) in team" :key="index" class="text-center group">
            <div class="relative mb-6 inline-block">
              <img :src="`/placeholder.svg?height=300&width=300`" :alt="member.name"
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

    <!-- CTA Section -->
    <section id="cta" class="bg-[#1B5E20] text-white py-24">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-6">Ready to Revolutionize Your Fish Farm?</h2>
        <p class="text-xl mb-12 text-gray-300">Join hundreds of farmers who trust Tanikan for efficient and sustainable
          fish farming solutions.</p>
        <div class="flex justify-center gap-6">
          <button
            class="bg-[#2E7D32] text-white font-bold py-4 px-8 rounded-full hover:bg-[#1B5E20] transition duration-300 flex items-center gap-2">
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

    <!-- Footer -->
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
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import {
  ArrowRight,
  AlertTriangle,
  XCircle,
  Lightbulb,
  Camera,
  Bell,
  Wind,
  Smartphone,
  Upload,
  Activity,
  Database,
  BarChart,
  Leaf,
  Scale,
  DollarSign,
  TrendingUp,
  Cpu,
  Wifi,
  Shield,
  Quote,
  Linkedin,
  Twitter,
  Phone,
  Facebook,
  Instagram,
  ChevronDown,
  X
} from 'lucide-vue-next'

const isNavbarVisible = ref(false)
const isDropdownOpen = ref(false)

const navItems = [
  { name: 'Vision', href: '#vision' },
  { name: 'Solution', href: '#solution' },
  { name: 'Features', href: '#features' },
  { name: 'How It Works', href: '#how-it-works' },
  { name: 'Benefits', href: '#benefits' },
  { name: 'Technology', href: '#technology' },
  { name: 'Testimonials', href: '#testimonials' },
  { name: 'Team', href: '#team' },
]

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

const team = [
  {
    name: 'Alice Johnson',
    role: 'CEO',
    image: '/placeholder.svg?height=300&width=300'
  },
  {
    name: 'Bob Williams',
    role: 'CTO',
    image: '/placeholder.svg?height=300&width=300'
  },
  {
    name: 'Carol Davis',
    role: 'Aquaculture Specialist',
    image: '/placeholder.svg?height=300&width=300'
  },
]

const handleScroll = () => {
  isNavbarVisible.value = window.scrollY > 50
}

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value
}

const closeDropdown = () => {
  isDropdownOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>