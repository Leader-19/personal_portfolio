<template>
    <section id="contact" class="py-20 bg-white">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-800 mb-12">
                Get In Touch
            </h2>

            <div class="grid md:grid-cols-2 gap-12 items-start">
                <!-- Left Column: Contact Info -->
                <div class="space-y-6">
                    <div v-for="contact in contactInfo" :key="contact.type" class="flex items-center space-x-4">
                        <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center">
                            <component :is="contact.icon" class="w-6 h-6 text-blue-600" />
                        </div>
                        <div>
                            <div class="font-medium text-gray-800">{{ contact.label }}</div>
                            <div class="text-gray-600">{{ contact.value }}</div>
                        </div>
                    </div>
                </div>

                <!-- Right Column: Google Map -->
                <div class="rounded-2xl overflow-hidden shadow-lg h-100">
                    <iframe class="w-full h-[600px] md:h-full"
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3018.2880262766494!2d104.88050867364694!3d11.550865044434758!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x310951add5e2cd81%3A0x171e0b69c7c6f7ba!2sPasserelles%20num%C3%A9riques%20Cambodia%20(PNC)!5e1!3m2!1sen!2skh!4v1756095188338!5m2!1sen!2skh"
                        style="border:0;" allowfullscreen="" loading="lazy"
                        referrerpolicy="no-referrer-when-downgrade"></iframe>
                </div>

            </div>
        </div>
    </section>
</template>

<script setup>
// ✅ Icon components without JSX
const MailIcon = { template: `<i class="fa-solid fa-envelope"></i>` }
const PhoneIcon = { template: `<i class="fa-solid fa-phone"></i>` }
const LocationIcon = { template: `<i class="fa-solid fa-location-dot"></i>` }

const contactInfo = [
    { type: 'email', label: 'Email', value: 'dinleader26@gmail.com', icon: MailIcon },
    { type: 'phone', label: 'Phone', value: '+855 69505726', icon: PhoneIcon },
    { type: 'location', label: 'Location', value: 'Phnom Penh, Cambodia', icon: LocationIcon }
]
</script>
