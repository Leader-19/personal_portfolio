<template>
    <section id="home"
        class="min-h-screen flex items-center justify-cente relative overflow-hidden">
        <!-- Animated background elements -->
        <div class="absolute inset-0">
            <div
                class="absolute top-10 sm:top-20 left-4 sm:left-20 w-32 h-32 sm:w-72 sm:h-72 bg-blue-500 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob">
            </div>
            <div
                class="absolute top-20 sm:top-40 right-4 sm:right-20 w-32 h-32 sm:w-72 sm:h-72 bg-yellow-500 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-2000">
            </div>
            <div
                class="absolute -bottom-4 sm:-bottom-8 left-8 sm:left-40 w-32 h-32 sm:w-72 sm:h-72 bg-pink-500 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-4000">
            </div>
        </div>

        <!-- Floating geometric shapes -->
        <div class="absolute inset-0 overflow-hidden">
            <div class="hidden sm:block absolute top-1/4 left-1/4 w-4 h-4 bg-white opacity-20 rotate-45 animate-float"></div>
            <div class="hidden sm:block absolute top-3/4 right-1/4 w-6 h-6 bg-blue-400 opacity-30 rounded-full animate-float-delayed">
            </div>
            <div class="absolute top-1/2 left-3/4 w-3 h-3 bg-purple-400 opacity-25 animate-pulse"></div>
            <div class="hidden sm:block absolute bottom-1/4 left-1/3 w-5 h-5 bg-pink-400 opacity-20 rotate-12 animate-bounce-slow">
            </div>
        </div>

        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 w-full">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 sm:gap-12 items-center min-h-screen lg:min-h-0">
                <!-- Left Column - Enhanced Text Content -->
                <div class="order-2 lg:order-1 text-center lg:text-left px-4 sm:px-0">
                    <!-- Enhanced typography with gradient text and better spacing -->
                    <div class="mb-4 sm:mb-6">
                        <p class="text-base sm:text-lg text-black-300 mb-2 tracking-wide">Hello, I'm</p>
                        <h1 class="text-3xl sm:text-5xl md:text-6xl lg:text-7xl font-bold mb-4 leading-tight">
                            <span
                                class="bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent animate-gradient">
                                Leader Din
                            </span>
                        </h1>
                    </div>

                    <!-- Enhanced role display with better styling -->
                    <div class="mb-6 sm:mb-8 h-12 sm:h-16 flex items-center justify-center lg:justify-start">
                        <p class="text-lg sm:text-2xl md:text-3xl text-black font-light">
                            <span class="text-blue-400">></span> {{ currentRole }}
                            <span class="animate-pulse text-blue-400">|</span>
                        </p>
                    </div>

                    <!-- Enhanced buttons with modern design and hover effects -->
                    <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 mb-6 sm:mb-8 px-4 sm:px-0">
                        <button
                            class="group relative bg-gradient-to-r from-blue-600 to-purple-600 text-white px-6 sm:px-8 py-3 sm:py-4 rounded-xl font-semibold overflow-hidden transition-all duration-300 hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/25 text-sm sm:text-base">
                            <span class="relative z-10">View My Work</span>
                            <div
                                class="absolute inset-0 bg-gradient-to-r from-purple-600 to-pink-600 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                            </div>
                        </button>
                        <button
                            class="group relative border-2 border-blue-400 text-blue-400 px-6 sm:px-8 py-3 sm:py-4 rounded-xl font-semibold overflow-hidden transition-all duration-300 hover:scale-105 hover:text-white text-sm sm:text-base">
                            <span class="relative z-10">Download CV</span>
                            <div
                                class="absolute inset-0 bg-gradient-to-r from-blue-600 to-purple-600 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                            </div>
                        </button>
                    </div>

                    <!-- Added social media links -->
                    <div class="flex justify-center lg:justify-start space-x-4 sm:space-x-6">
                        <a href="#"
                            class="text-gray-400 hover:text-blue-400 transition-colors duration-300 transform hover:scale-110">
                            <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z" />
                            </svg>
                        </a>
                        <a href="#"
                            class="text-gray-400 hover:text-blue-400 transition-colors duration-300 transform hover:scale-110">
                            <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
                            </svg>
                        </a>
                        <a href="#"
                            class="text-gray-400 hover:text-blue-400 transition-colors duration-300 transform hover:scale-110">
                            <svg class="w-5 h-5 sm:w-6 sm:h-6" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
                            </svg>
                        </a>
                    </div>
                </div>

                <!-- Right Column - Enhanced Image -->
                <div class="order-1 lg:order-2 flex justify-center lg:justify-end">
                    <div class="relative">
                        <!-- Glow background -->
                        <div
                            class="absolute inset-0 bg-gradient-to-r from-blue-400 to-purple-600 rounded-full blur-2xl opacity-30 animate-pulse">
                        </div>

                        <!-- Profile Picture -->
                        <img src="/profile.JPG" alt="Profile Picture"
                            class="relative w-64 h-64 sm:w-80 sm:h-80 rounded-full shadow-2xl object-cover border-4 border-white/20 backdrop-blur-sm hover:scale-105 transition-transform duration-300">

                        <!-- Floating tech badges -->
                        <div
                            class="absolute -top-2 -right-2 sm:-top-4 sm:-right-4 bg-blue-500 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-bounce-slow">
                            Vue.js
                        </div>

                        <div
                            class="absolute -bottom-2 -left-2 sm:-bottom-4 sm:-left-4 bg-purple-500 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-float">
                            Node.js
                        </div>

                        <div
                            class="absolute top-1/2 -right-8 sm:-right-12 bg-pink-500 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-float-delayed">
                            Laravel
                        </div>

                        <div
                            class="absolute -top-4 sm:-top-6 left-1/2 -translate-x-1/2 bg-yellow-500 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-float">
                            JavaScript
                        </div>

                        <div
                            class="absolute bottom-1/2 -left-8 sm:-left-12 bg-green-500 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-bounce-slow">
                            PHP
                        </div>

                        <div
                            class="absolute bottom-6 sm:bottom-10 right-1/2 translate-x-1/2 bg-gray-700 text-white px-2 py-1 sm:px-3 sm:py-1 rounded-full text-xs sm:text-sm font-semibold animate-float-delayed">
                            MySQL
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Web Developer', 'Frontend Developer', 'Backend Developer', 'DevOps Engineer']
const currentRole = ref('')
let roleIndex = 0

const typeRole = () => {
    const role = roles[roleIndex]
    let charIndex = 0

    const typeInterval = setInterval(() => {
        currentRole.value = role.substring(0, charIndex + 1)
        charIndex++

        if (charIndex === role.length) {
            clearInterval(typeInterval)
            setTimeout(() => {
                roleIndex = (roleIndex + 1) % roles.length
                currentRole.value = ''
                typeRole()
            }, 2000)
        }
    }, 100)
}

onMounted(() => {
    typeRole()
})
</script>

<style scoped>
@keyframes blob {
    0% {
        transform: translate(0px, 0px) scale(1);
    }

    33% {
        transform: translate(30px, -50px) scale(1.1);
    }

    66% {
        transform: translate(-20px, 20px) scale(0.9);
    }

    100% {
        transform: translate(0px, 0px) scale(1);
    }
}

@keyframes float {

    0%,
    100% {
        transform: translateY(0px);
    }

    50% {
        transform: translateY(-20px);
    }
}

@keyframes float-delayed {

    0%,
    100% {
        transform: translateY(0px);
    }

    50% {
        transform: translateY(-15px);
    }
}

@keyframes bounce-slow {

    0%,
    100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-10px);
    }
}

@keyframes gradient {

    0%,
    100% {
        background-size: 200% 200%;
        background-position: left center;
    }

    50% {
        background-size: 200% 200%;
        background-position: right center;
    }
}

.animate-blob {
    animation: blob 7s infinite;
}

.animation-delay-2000 {
    animation-delay: 2s;
}

.animation-delay-4000 {
    animation-delay: 4s;
}

.animate-float {
    animation: float 6s ease-in-out infinite;
}

.animate-float-delayed {
    animation: float-delayed 8s ease-in-out infinite;
}

.animate-bounce-slow {
    animation: bounce-slow 3s ease-in-out infinite;
}

.animate-gradient {
    animation: gradient 3s ease infinite;
}
</style>
