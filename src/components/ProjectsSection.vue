<template>
  <section id="projects" class="py-20 bg-gray-50">
    <div class="max-w-6xl mx-auto px-4">
      <!-- Added fade-up animation for title -->
      <transition name="fade-up" appear>
        <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Projects</h2>
      </transition>
      
      <!-- Added transition-group for staggered project card animations -->
      <transition-group name="project-card" tag="div" class="grid md:grid-cols-2 lg:grid-cols-3 gap-8" appear>
        <div v-for="(project, index) in projects" :key="project.id" 
             :style="{ '--delay': index * 0.1 + 's' }"
             class="project-card bg-white rounded-lg shadow-lg overflow-hidden group cursor-pointer">
          <!-- Enhanced image with hover zoom effect -->
          <div class="image-container overflow-hidden">
            <img :src="project.image" :alt="project.title" 
                 class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110">
          </div>
          <div class="p-6">
            <!-- Added hover animation for title -->
            <h3 class="text-xl font-bold text-gray-800 mb-2 transition-colors duration-300 group-hover:text-blue-600">
              {{ project.title }}
            </h3>
            <p class="text-gray-600 mb-4 transition-colors duration-300 group-hover:text-gray-700">
              {{ project.description }}
            </p>
            <!-- Added staggered animation for technology tags -->
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="(tech, techIndex) in project.technologies" :key="tech"
                    :style="{ '--tech-delay': techIndex * 0.05 + 's' }"
                    class="tech-tag bg-blue-100 text-blue-800 text-xs px-2 py-1 rounded transition-all duration-300 hover:bg-blue-200 hover:scale-105">
                {{ tech }}
              </span>
            </div>
            <!-- Enhanced link hover effects -->
            <div class="flex space-x-4">
              <a :href="project.liveUrl" target="_blank" 
                 class="link-button text-blue-600 hover:text-blue-800 font-medium transition-all duration-300 hover:scale-105 hover:underline">
                Live Demo
              </a>
              <a :href="project.githubUrl" target="_blank" 
                 class="link-button text-gray-600 hover:text-gray-800 font-medium transition-all duration-300 hover:scale-105 hover:underline">
                GitHub
              </a>
            </div>
          </div>
        </div>
      </transition-group>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    id: 1,
    title: 'Weather Website',
    description: 'A responsive weather application that provides real-time weather updates for any location, with interactive forecasts and a user-friendly interface.',
    image: '../../project3.png',
    technologies: ['HTML', 'CSS', 'Bootstrap', 'JavaScript'],
    liveUrl: '#',
    githubUrl: '#'
  },
  {
    id: 2,
    title: 'POS System',
    description: 'A point of sale and inventory management system to track sales, manage stock, and generate reports with visual charts.',
    image: '../../project2.png',
    technologies: ['Bootstrap', 'PHP', 'MySQL', 'Chart.js'],
    liveUrl: '#',
    githubUrl: '#'
  },
  {
    id: 3,
    title: 'Leave Management System',
    description: 'A web-based system that allows employees to request leave and managers to approve or reject requests, with secure authentication and database integration.',
    image: '../../project.png',
    technologies: ['Bootstrap', 'Laravel', 'MySQL'],
    liveUrl: '#',
    githubUrl: '#'
  }
]
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

/* Project card entrance animations */
.project-card-enter-active {
  transition: all 0.6s ease-out;
  transition-delay: var(--delay);
}

.project-card-enter-from {
  opacity: 0;
  transform: translateY(50px) scale(0.9);
}

/* Project card hover effects */
.project-card {
  transition: all 0.3s ease-out;
  animation: slideInUp 0.6s ease-out forwards;
  animation-delay: var(--delay);
  opacity: 0;
}

@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(50px) scale(0.9);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

/* Technology tag animations */
.tech-tag {
  animation: fadeInScale 0.4s ease-out forwards;
  animation-delay: calc(var(--delay) + var(--tech-delay) + 0.3s);
  opacity: 0;
  transform: scale(0.8);
}

@keyframes fadeInScale {
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Link button hover effects */
.link-button {
  position: relative;
  overflow: hidden;
}

.link-button::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: currentColor;
  transition: width 0.3s ease-out;
}

.link-button:hover::before {
  width: 100%;
}

/* Image container effects */
.image-container {
  position: relative;
}

.image-container::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(59, 130, 246, 0.1), rgba(147, 51, 234, 0.1));
  opacity: 0;
  transition: opacity 0.3s ease-out;
}

.group:hover .image-container::after {
  opacity: 1;
}

/* Responsive animations */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
</style>
