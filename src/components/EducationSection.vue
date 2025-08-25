<template>
    <section id="education" name="Education" class="py-20 bg-white">
        <div class="max-w-6xl mx-auto px-4">
            <!-- Added fade-in animation for the title -->
            <transition name="fade-up" appear>
                <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Education</h2>
            </transition>

            <div class="max-w-4xl mx-auto">
                <div class="relative">
                    <!-- Timeline line -->
                    <!-- Added growing animation for the timeline line -->
                    <transition name="grow-line" appear>
                        <div class="absolute left-4 md:left-1/2 transform md:-translate-x-1/2 w-0.5 h-full bg-blue-200 timeline-line">
                        </div>
                    </transition>

                    <!-- Added staggered animations for timeline items -->
                    <transition-group name="timeline-item" appear>
                        <div v-for="(edu, index) in education" :key="index" 
                             class="relative flex items-center mb-8 timeline-item"
                             :class="index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse'"
                             :style="{ 'animation-delay': `${index * 0.3}s` }">

                            <!-- Timeline dot -->
                            <!-- Added pulse animation for timeline dots -->
                            <div class="absolute left-4 md:left-1/2 transform md:-translate-x-1/2 w-4 h-4 bg-blue-600 rounded-full border-4 border-white shadow-lg z-10 timeline-dot">
                            </div>

                            <!-- Content -->
                            <div class="ml-12 md:ml-0 md:w-1/2" :class="index % 2 === 0 ? 'md:pr-8' : 'md:pl-8'">
                                <!-- Added hover animation for content cards -->
                                <div class="bg-gray-50 rounded-lg p-6 shadow-md flex flex-col md:flex-row items-start gap-4 education-card">

                                    <!-- Education Image -->
                                    <img v-if="edu.image" :src="edu.image" alt="Education Logo"
                                        class="w-16 h-16 object-contain rounded-md shadow-md education-image" />

                                    <!-- Education Info -->
                                    <div>
                                        <div class="text-blue-600 font-semibold mb-2">{{ edu.period }}</div>
                                        <h3 class="text-xl font-bold text-gray-800 mb-2">{{ edu.degree }}</h3>
                                        <p class="text-gray-600 mb-2">{{ edu.institution }}</p>
                                        <p class="text-gray-500 text-sm">{{ edu.description }}</p>
                                        <div v-if="edu.gpa" class="mt-2">
                                            <span class="text-sm text-gray-600">GPA: {{ edu.gpa }}</span>
                                        </div>
                                    </div>

                                </div>
                            </div>
                        </div>
                    </transition-group>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const education = [
    {
        period: '2012 - 2017',
        degree: 'Primary Education',
        institution: 'Prey Phangs Primary School',
        description: 'Completed grades 1 to 6 with a strong foundation in general education subjects.',
        image: '../../primary.jpg'
    },
    {
        period: '2018 - 2023',
        degree: 'Secondary & High School Education',
        institution: 'Koas Krala High School',
        description: 'Studied from grades 7 to 12, developing academic skills and preparing for higher education.',
        image: '../../high_school.jpg'
    },
    {
        period: '2024 - 2025',
        degree: 'Associate Degree in Computer Science',
        institution: 'Passerelles Numériques Cambodia',
        description: 'Specialized in computer science with a focus on web programming, databases, and IT fundamentals.',
        image: '../../pnc.jpg'
    }
]

onMounted(() => {
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('animate-in')
            }
        })
    }, { threshold: 0.1 })

    document.querySelectorAll('.timeline-item').forEach(item => {
        observer.observe(item)
    })
})
</script>

<style scoped>
/* Added comprehensive animation styles */

/* Fade up animation for title */
.fade-up-enter-active {
    transition: all 0.8s ease-out;
}

.fade-up-enter-from {
    opacity: 0;
    transform: translateY(30px);
}

/* Growing timeline line animation */
.grow-line-enter-active {
    transition: all 1.5s ease-out;
}

.grow-line-enter-from {
    height: 0 !important;
}

.timeline-line {
    animation: growLine 1.5s ease-out;
}

@keyframes growLine {
    from {
        height: 0;
    }
    to {
        height: 100%;
    }
}

/* Timeline item animations */
.timeline-item-enter-active {
    transition: all 0.6s ease-out;
}

.timeline-item-enter-from {
    opacity: 0;
    transform: translateX(-50px);
}

.timeline-item:nth-child(even) .timeline-item-enter-from {
    transform: translateX(50px);
}

/* Timeline dot pulse animation */
.timeline-dot {
    animation: dotPulse 2s infinite;
}

@keyframes dotPulse {
    0% {
        box-shadow: 0 0 0 0 rgba(59, 130, 246, 0.7);
    }
    70% {
        box-shadow: 0 0 0 10px rgba(59, 130, 246, 0);
    }
    100% {
        box-shadow: 0 0 0 0 rgba(59, 130, 246, 0);
    }
}

/* Education card hover effects */
.education-card {
    transition: all 0.3s ease;
    transform: translateY(0);
}

.education-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
}

/* Education image hover effect */
.education-image {
    transition: all 0.3s ease;
}

.education-card:hover .education-image {
    transform: scale(1.1);
}

/* Scroll-triggered animations */
.timeline-item {
    opacity: 0;
    transform: translateY(30px);
    transition: all 0.6s ease-out;
}

.timeline-item.animate-in {
    opacity: 1;
    transform: translateY(0);
}

/* Staggered animation delays */
.timeline-item:nth-child(1) { animation-delay: 0.1s; }
.timeline-item:nth-child(2) { animation-delay: 0.4s; }
.timeline-item:nth-child(3) { animation-delay: 0.7s; }

/* Responsive animations */
@media (max-width: 768px) {
    .timeline-item-enter-from {
        transform: translateX(-30px);
    }
    
    .timeline-item:nth-child(even) .timeline-item-enter-from {
        transform: translateX(-30px);
    }
}
</style>
