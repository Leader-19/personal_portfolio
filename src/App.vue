<template>
  <div class="min-h-screen bg-gray-50">
    <!-- Navigation -->
    <nav class="fixed top-0 w-full bg-white shadow-md z-50">
      <div class="max-w-6xl mx-auto px-4">
        <div class="flex justify-between items-center py-4">
          <!-- Logo -->
          <div class="text-xl font-bold text-gray-800">Leader Din</div>

          <!-- Desktop Menu -->
          <div class="hidden md:flex space-x-6">
            <a
              v-for="section in sections"
              :key="section.id"
              :href="`#${section.id}`"
              @click="scrollToSection(section.id)"
              class="transition-colors"
              :class="activeSection === section.id
                        ? 'text-blue-600 font-semibold border-b-2 border-blue-600 pb-1'
                        : 'text-gray-600 hover:text-blue-600'">
              {{ section.name }}
            </a>
          </div>

          <!-- Mobile Menu Button -->
          <button @click="toggleMobileMenu" class="md:hidden">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>

        <!-- Mobile Menu -->
        <div v-if="mobileMenuOpen" class="md:hidden pb-4">
          <a
            v-for="section in sections"
            :key="section.id"
            :href="`#${section.id}`"
            @click="scrollToSection(section.id)"
            class="block py-2 transition-colors"
            :class="activeSection === section.id
                      ? 'text-blue-600 font-semibold'
                      : 'text-gray-600 hover:text-blue-600'">
            {{ section.name }}
          </a>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="pt-16">
      <section id="home"><HomeSection /></section>
      <section id="about"><AboutSection /></section>
      <section id="skills"><SkillsSection /></section>
      <section id="education"><EducationSection /></section>
      <section id="projects"><ProjectsSection /></section>
      <section id="contact"><ContactSection /></section>
      <FooterSection />
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import HomeSection from './components/HomeSection.vue'
import AboutSection from './components/AboutSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import EducationSection from './components/EducationSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

const mobileMenuOpen = ref(false)
const activeSection = ref('home')

const sections = [
  { id: 'home', name: 'Home' },
  { id: 'about', name: 'About' },
  { id: 'skills', name: 'Skills' },
  { id: 'education', name: 'Education' },
  { id: 'projects', name: 'Projects' },
  { id: 'contact', name: 'Contact' }
]

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const scrollToSection = (sectionId) => {
  document.getElementById(sectionId)?.scrollIntoView({ behavior: 'smooth' })
  mobileMenuOpen.value = false
  activeSection.value = sectionId
}

// IntersectionObserver to detect active section
let observer
onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id
        }
      })
    },
    { threshold: 0.6 } // section is active when 60% is visible
  )

  sections.forEach((section) => {
    const el = document.getElementById(section.id)
    if (el) observer.observe(el)
  })
})

onBeforeUnmount(() => {
  if (observer) observer.disconnect()
})
</script>
