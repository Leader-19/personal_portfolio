<template>
    <section id="about" class="py-20 bg-white">
        <div class="max-w-6xl mx-auto px-4">
            <h2 
                class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12 transition-all duration-1000"
                :class="{ 'opacity-100 translate-y-0': isVisible, 'opacity-0 translate-y-8': !isVisible }"
            >
                About Me
            </h2>
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div 
                    class="transition-all duration-1000 delay-300"
                    :class="{ 'opacity-100 translate-x-0': isVisible, 'opacity-0 -translate-x-8': !isVisible }"
                >
                    <img src="../../public/about.JPG" alt="About Me" class="rounded-lg shadow-lg w-full hover:shadow-xl transition-shadow duration-300">
                </div>

                <div 
                    class="transition-all duration-1000 delay-500"
                    :class="{ 'opacity-100 translate-x-0': isVisible, 'opacity-0 translate-x-8': !isVisible }"
                >
                    <p class="text-lg text-gray-600 mb-6 leading-relaxed">
                        My education journey started at <span class="font-semibold">Prey Phngeas Primary School</span>,
                        where I completed grades 1 to 6. I then continued my studies at
                        <span class="font-semibold">Koas Krala High School</span>, completing grades 7 to 12.
                        During this time, I successfully passed the <span class="font-semibold">Baccalaureate
                            (BacII)</span>
                        examination with a <span class="font-semibold">Grade B</span> and earned my
                        <span class="font-semibold">Secondary School Diploma</span>.
                    </p>

                    <p class="text-lg text-gray-600 mb-8 leading-relaxed">
                        Later, I pursued higher education at <span class="font-semibold">Passerelles Numériques
                            Cambodia</span>,
                        where I earned an <span class="font-semibold">Associate Degree in Computer Science</span>.
                        There, I specialized in <span class="font-semibold">Web programming, databases, and IT
                            fundamentals</span>,
                        which strengthened my passion for software development and technology.
                    </p>

                    <div class="grid grid-cols-2 gap-6">
                        <div 
                            v-for="(stat, index) in stats" 
                            :key="stat.label" 
                            class="text-center transition-all duration-700"
                            :class="{ 
                                'opacity-100 translate-y-0': isVisible, 
                                'opacity-0 translate-y-4': !isVisible 
                            }"
                            :style="{ transitionDelay: `${800 + index * 150}ms` }"
                        >
                            <div class="text-3xl font-bold text-blue-600 mb-2 hover:scale-110 transition-transform duration-300">
                                {{ animatedStats[index] }}{{ stat.suffix }}
                            </div>
                            <div class="text-gray-600">{{ stat.label }}</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isVisible = ref(false)
const animatedStats = ref([0, 0, 0, 0])

const stats = [
    { value: 7, suffix: '+', label: 'Projects Completed' },
    { value: 2, suffix: '+', label: 'Happy Clients' },
    { value: 1, suffix: '+', label: 'Years Experience' },
    { value: 10, suffix: '+', label: 'Technologies' }
]

let observer = null

const animateCounters = () => {
    stats.forEach((stat, index) => {
        let current = 0
        const increment = stat.value / 50 // Animate over 50 steps
        const timer = setInterval(() => {
            current += increment
            if (current >= stat.value) {
                current = stat.value
                clearInterval(timer)
            }
            animatedStats.value[index] = Math.floor(current)
        }, 30) // Update every 30ms for smooth animation
    })
}

onMounted(() => {
    observer = new IntersectionObserver(
        (entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting && !isVisible.value) {
                    isVisible.value = true
                    // Start counter animations after a delay
                    setTimeout(() => {
                        animateCounters()
                    }, 1000)
                }
            })
        },
        { threshold: 0.3 }
    )
    
    const section = document.getElementById('about')
    if (section) {
        observer.observe(section)
    }
})

onUnmounted(() => {
    if (observer) {
        observer.disconnect()
    }
})
</script>

