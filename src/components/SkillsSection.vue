<template>
  <section id="skills" class="py-20 bg-gray-50" name="Skills">
    <div class="max-w-6xl mx-auto px-4">
      <transition name="fade-up" appear>
        <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">Skills</h2>
      </transition>

      <!-- Hard Skills -->
      <div class="space-y-8">
        <transition name="slide-up" appear>
          <div class="bg-white rounded-lg shadow-lg p-6">
            <h3 class="text-xl font-bold text-gray-800 mb-6 text-center">Programming Languages</h3>
            <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
              <transition-group name="stagger" appear>
                <div 
                  v-for="(skill, index) in hardSkills" 
                  :key="skill.name" 
                  class="skill-item"
                  :style="{ '--delay': index * 0.1 + 's' }"
                >
                  <div class="skill-card flex flex-col items-center p-4 bg-gray-50 rounded-lg hover:bg-blue-50 transition-all duration-300 hover:scale-105 hover:shadow-md">
                    <!-- Use image instead of icon -->
                    <div class="skill-icon-container mb-3">
                      <img :src="skill.image" :alt="skill.name" class="skill-icon w-12 h-12 object-contain" />
                    </div>
                    <span class="text-gray-700 font-medium text-sm text-center mb-2">{{ skill.name }}</span>
                    <div class="w-full bg-gray-200 rounded-full h-2 overflow-hidden">
                      <div 
                        class="progress-bar bg-gradient-to-r from-blue-500 to-blue-600 h-2 rounded-full transition-all duration-1000 ease-out"
                        :class="{ 'animate-progress': isVisible }"
                        :style="{ width: isVisible ? `${skill.level}%` : '0%' }"
                      ></div>
                    </div>
                    <span class="text-xs text-gray-500 mt-1">{{ skill.level }}%</span>
                  </div>
                </div>
              </transition-group>
            </div>
          </div>
        </transition>

        <!-- Tools -->
        <transition name="slide-up" appear>
          <div class="bg-white rounded-lg shadow-lg p-6">
            <h3 class="text-xl font-bold text-gray-800 mb-6 text-center">Tools & Technologies</h3>
            <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-8 gap-4">
              <transition-group name="stagger" appear>
                <div 
                  v-for="(tool, index) in tools" 
                  :key="tool.name"
                  class="tool-card flex flex-col items-center p-4 bg-gray-50 rounded-lg hover:bg-blue-50 transition-all duration-300 hover:scale-105 hover:shadow-md hover:rotate-2"
                  :style="{ '--delay': (index * 0.05 + 0.5) + 's' }"
                >
                  <!-- Use image instead of icon -->
                  <div class="tool-icon-container mb-3">
                    <img :src="tool.image" :alt="tool.name" class="tool-icon w-12 h-12 object-contain" />
                  </div>
                  <span class="text-gray-700 font-medium text-sm text-center">{{ tool.name }}</span>
                </div>
              </transition-group>
            </div>
          </div>
        </transition>

        <!-- Soft Skills -->
        <transition name="slide-up" appear>
          <div class="bg-white rounded-lg shadow-lg p-6">
            <h3 class="text-xl font-bold text-gray-800 mb-6 text-center">Soft Skills</h3>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
              <transition-group name="stagger" appear>
                <div 
                  v-for="(skill, index) in softSkills" 
                  :key="skill.name"
                  class="soft-skill-card flex items-center space-x-3 p-3 bg-gray-50 rounded-lg hover:bg-blue-50 transition-all duration-300 hover:scale-105 hover:shadow-md"
                  :style="{ '--delay': (index * 0.1 + 1) + 's' }"
                >
                  <!-- Soft skills keep using emoji icons -->
                  <div class="skill-emoji w-8 h-8 flex items-center justify-center text-lg">
                    {{ skill.icon }}
                  </div>
                  <span class="text-gray-700 font-medium">{{ skill.name }}</span>
                </div>
              </transition-group>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isVisible = ref(false)

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true
  }, 500)
})

const hardSkills = [
  { name: 'HTML', level: 100, image: '../../html.png' },
  { name: 'CSS', level: 100, image: '../../css.png' },
  { name: 'SASS', level: 90, image: '../../sass.png' },
  { name: 'JavaScript', level: 80, image: '../../js.png' },
  { name: 'PHP', level: 90, image: '../../php.png' },
  { name: 'Laravel', level: 90, image: '../../laravel.png' },
  { name: 'Boostrap', level: 90, image: '../../boostrap.jpg' },
  { name: 'Tailwindcss', level: 90, image: '../../tailwind.png' },
  { name: 'Vue.js', level: 85, image: '../../vue.png' },
  { name: 'Node.js', level: 75, image: '../../node.png' },
  { name: 'Python', level: 65, image: '../../python.png' },
  { name: 'OOP + TypeScript', level: 70, image: '../../ts.png' }
]

const tools = [
  { name: 'Git', image: '../../git.png' },
  { name: 'GitHub', image: '../../github.png' },
  { name: 'Jira', image: '../../jira.png' },
  { name: 'Docker', image: '../../docker.png' },
  { name: 'AWS', image: '../../aws.png' },
  { name: 'MySQL', image: '../../mysql.png' },
  { name: 'Figma', image: '../../figma.png' },
  { name: 'VS Code', image: '../../vs.png' },
  { name: 'Firebase', image: '../../firebase.png' },
  { name: 'Vercel', image: '../../vercel.png' },
  { name: 'Netlify', image: '../../net.png' },
  { name: 'Power BI', image: '../../power.png' },
  { name: 'ChatGPT', image: '../../chatgpt.png' },
  { name: 'v0', image: '../../v0.png' },
  { name: 'Grok', image: '../../grok.png' },
  { name: 'DeepSeek', image: '../../deep.png' },
]

const softSkills = [
  { name: 'Problem Solving', icon: '🧩' },
  { name: 'Team Collaboration', icon: '🤝' },
  { name: 'Communication', icon: '💬' },
  { name: 'Time Management', icon: '⏰' },
  { name: 'Leadership', icon: '👑' },
  { name: 'Adaptability', icon: '🔄' },
  { name: 'Critical Thinking', icon: '🧠' },
  { name: 'Creativity', icon: '💡' }
]
</script>

<style scoped>
/* Added comprehensive animation styles */

/* Fade up animation for main title */
.fade-up-enter-active {
  transition: all 0.8s ease-out;
}

.fade-up-enter-from {
  opacity: 0;
  transform: translateY(30px);
}

/* Slide up animation for sections */
.slide-up-enter-active {
  transition: all 0.6s ease-out;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateY(50px);
}

/* Staggered animation for skill items */
.stagger-enter-active {
  transition: all 0.6s ease-out;
  transition-delay: var(--delay);
}

.stagger-enter-from {
  opacity: 0;
  transform: translateY(30px) scale(0.9);
}

/* Skill card hover animations */
.skill-card {
  transform-origin: center;
}

.skill-card:hover .skill-icon {
  animation: bounce 0.6s ease-in-out;
}

.tool-card:hover .tool-icon {
  animation: wiggle 0.5s ease-in-out;
}

.soft-skill-card:hover .skill-emoji {
  animation: pulse-emoji 0.6s ease-in-out;
}

/* Progress bar animation */
.progress-bar {
  transform-origin: left;
}

.animate-progress {
  animation: fillProgress 1.5s ease-out forwards;
}

/* Keyframe animations */
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-10px);
  }
  60% {
    transform: translateY(-5px);
  }
}

@keyframes wiggle {
  0%, 100% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(-5deg);
  }
  75% {
    transform: rotate(5deg);
  }
}

@keyframes pulse-emoji {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
}

@keyframes fillProgress {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

/* Enhanced hover effects */
.skill-card:hover,
.tool-card:hover,
.soft-skill-card:hover {
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

.tool-card:hover {
  transform: translateY(-5px) scale(1.05) rotate(2deg);
}

/* Icon container animations */
.skill-icon-container,
.tool-icon-container {
  transition: transform 0.3s ease;
}

.skill-card:hover .skill-icon-container {
  transform: scale(1.1);
}

.tool-card:hover .tool-icon-container {
  transform: scale(1.1) rotate(-2deg);
}
</style>
