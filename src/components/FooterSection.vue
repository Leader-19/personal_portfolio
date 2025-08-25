<template>
    <footer class="bg-gray-900 text-gray-300 py-8 mt-16">
        <div class="max-w-6xl mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8">

            <!-- About Me -->
            <div>
                <h2 class="text-lg font-semibold text-white mb-3">About Me</h2>
                <p class="text-sm leading-relaxed">
                    I'm a passionate web developer focused on building responsive and user-friendly applications with
                    modern technologies.
                </p>
            </div>

            <!-- Quick Links -->
            <div>
                <h2 class="text-lg font-semibold text-white mb-3">Quick Links</h2>
                <ul class="space-y-2 text-sm">
                    <li><a href="#projects" class="hover:text-blue-400 transition">Projects</a></li>
                    <li><a href="#skills" class="hover:text-blue-400 transition">Skills</a></li>
                    <li><a href="#contact" class="hover:text-blue-400 transition">Contact</a></li>
                </ul>
            </div>

            <!-- Social Media -->
            <div>
                <h2 class="text-lg font-semibold text-white mb-3">Connect</h2>
                <div class="flex space-x-4">
                    <a href="https://github.com/Leader-19" target="_blank" class="hover:text-blue-400 transition">
                        <i class="fa-brands fa-github text-xl"></i>
                    </a>
                    <a href="https://www.linkedin.com/in/leader-din-093557332/" target="_blank"
                        class="hover:text-blue-400 transition">
                        <i class="fa-brands fa-linkedin text-xl"></i>
                    </a>
                    <a href="dinleader200@gmail.com" class="hover:text-blue-400 transition">
                        <i class="fa-solid fa-envelope text-xl"></i>
                    </a>

                    <!-- Facebook -->
                    <a href="https://www.facebook.com/leader.dl" target="_blank"
                        class="hover:text-blue-400 transition">
                        <i class="fa-brands fa-facebook text-xl"></i>
                    </a>

                    <!-- Telegram -->
                    <a href="" target="_blank" class="hover:text-blue-400 transition">
                        <i class="fa-brands fa-telegram text-xl"></i>
                    </a>
                </div>
            </div>
        </div>

        <!-- Bottom Bar -->
        <div class="mt-8 border-t border-gray-700 pt-4 text-center text-sm text-gray-500">
            © {{ new Date().getFullYear() }} Leader Din. Web Development student.
        </div>
    </footer>
</template>

<script setup>
// No logic needed yet, but you can add reactive data if needed
</script>
