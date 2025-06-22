
  <template>
    <div class="bg-gray-100 min-h-screen py-12 px-4 sm:px-6 lg:px-8">
      <!-- Slideshow Section -->
      <section class="pb-12">
        <div class="w-full">
          <div class="relative">
            <!-- Slides -->
            <div class="overflow-hidden">
              <div class="flex transition-transform duration-500 ease-in-out" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
                <div v-for="(slide, index) in slides" :key="index" class="flex-shrink-0 w-full">
                  <div class="relative">
                    <img :src="slide.image" :alt="slide.caption" class="w-full h-[500px] object-cover rounded-lg shadow-lg" />
                    <div class="absolute bottom-0 left-0 right-0 bg-black bg-opacity-50 text-white p-4">
                      <h3 class="text-xl font-semibold">{{ slide.caption }}</h3>
                      <p class="text-sm">{{ slide.description }}</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- Navigation Arrows -->
            <button @click="prevSlide" class="absolute left-4 top-1/2 transform -translate-y-1/2 bg-green-600 text-white p-2 rounded-full hover:bg-green-700">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
              </svg>
            </button>
            <button @click="nextSlide" class="absolute right-4 top-1/2 transform -translate-y-1/2 bg-green-600 text-white p-2 rounded-full hover:bg-green-700">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
              </svg>
            </button>
            <!-- Dots -->
            <div class="absolute bottom-4 left-0 right-0 flex justify-center space-x-2">
              <button
                v-for="(slide, index) in slides"
                :key="index"
                @click="goToSlide(index)"
                :class="['w-3 h-3 rounded-full', currentSlide === index ? 'bg-green-600' : 'bg-gray-300']"
              ></button>
            </div>
          </div>
        </div>


           <!-- Contact Information Section -->
    <section class="max-w-6xl mx-auto mb-12">
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4 sm:gap-6 mt-11">
        <!-- Location Card -->
        <div class="bg-white p-3 sm:p-4 rounded-lg shadow-md text-center hover:shadow-lg transition transform hover:scale-105">
          <div class="flex justify-center mb-1 sm:mb-2">
            <svg class="w-6 sm:w-8 h-6 sm:h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
          </div>
          <h3 class="text-base sm:text-lg font-semibold text-gray-700">Location</h3>
          <p class="text-sm sm:text-base text-gray-600">371 Phum Tropeang Chhuk<br />(Borey Soria),<br />Sangkat Tek Thla, Khan Sen Sok,<br />Phnom Penh</p>
        </div>

        <!-- Phone Number Card -->
        <div class="bg-orange-500 p-3 sm:p-4 rounded-lg shadow-md text-center text-white hover:shadow-lg transition transform hover:scale-105">
          <div class="flex justify-center mb-1 sm:mb-2">
            <svg class="w-6 sm:w-8 h-6 sm:h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
          </div>
          <h3 class="text-base sm:text-lg font-semibold">Phone Number</h3>
          <p class="text-sm sm:text-base">+855 6740 8241<br />+855 9763 13871</p>
        </div>

        <!-- Email Address Card -->
        <div class="bg-white p-3 sm:p-4 rounded-lg shadow-md text-center hover:shadow-lg transition transform hover:scale-105">
          <div class="flex justify-center mb-1 sm:mb-2">
            <svg class="w-6 sm:w-8 h-6 sm:h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </div>
          <h3 class="text-base sm:text-lg font-semibold text-gray-700">Email Address</h3>
          <p class="text-sm sm:text-base">FruitShop@Cambodia.com<br />FreshFruit@Cambodia.com</p>
        </div>

        <!-- Facebook Page Card -->
        <div class="bg-white p-3 sm:p-4 rounded-lg shadow-md text-center hover:shadow-lg transition transform hover:scale-105">
          <div class="flex justify-center mb-1 sm:mb-2">
            <svg class="w-6 sm:w-8 h-6 sm:h-8 text-green-600" fill="currentColor" viewBox="0 0 24 24">
              <path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z" />
            </svg>
          </div>
          <h3 class="text-base sm:text-lg font-semibold text-gray-700">Facebook Page</h3>
          <p class="text-sm sm:text-base">Online Shop Page<br />Fruit Shop Cambodia</p>
        </div>
      </div>
    </section>

      </section>

      <!-- Title -->
      <div class="max-w-3xl mx-auto text-center mb-10">
        <h1 class="text-4xl font-extrabold text-green-700">Get in Touch</h1>
        <p class="mt-3 text-gray-600 text-lg">
          We'd love to hear from you. Reach out for inquiries, partnerships, or just a friendly hello!
        </p>
      </div>

      <!-- Content Grid -->
      <div class="max-w-6xl mx-auto grid md:grid-cols-2 gap-8">
        <!-- Contact Form -->
        <div class="bg-white p-6 rounded-xl shadow-md">
          <form @submit.prevent="submitForm" class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Your Name</label>
              <input type="text" v-model="form.name" required class="mt-1 w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-green-500 focus:border-green-500" />
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Email</label>
              <input type="email" v-model="form.email" required class="mt-1 w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-green-500 focus:border-green-500" />
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Message</label>
              <textarea v-model="form.message" rows="4" required class="mt-1 w-full px-4 py-2 border rounded-md focus:outline-none focus:ring-green-500 focus:border-green-500"></textarea>
            </div>
            <button type="submit" class="w-full bg-green-600 text-white py-2 rounded-lg hover:bg-green-700 transition">
              Send Message
            </button>
          </form>
        </div>

        <!-- Info + Map -->
        <div class="flex flex-col justify-center space-y-6 rounded-xl shadow-md text-gray-700 bg-gray-50 p-4">
          <div>
            <h2 class="text-xl font-semibold text-green-600 mb-1">Visit Us</h2>
            <p>Passerelles numériques Cambodia (PNC)<br />Phnom Penh, Cambodia</p>
          </div>
          <div>
            <h2 class="text-xl font-semibold text-green-600 mb-1">Phone</h2>
            <p>+855 123 456 789</p>
          </div>
          <div>
            <h2 class="text-xl font-semibold text-green-600 mb-1">Email</h2>
            <p>contact@pnc-cambodia.org</p>
          </div>

          <!-- Google Maps Embed -->
          <div class="h-64 rounded-xl overflow-hidden shadow-md">
            <iframe
              class="w-full h-full"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15641.69220593573!2d104.8730836!3d11.5508598!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x310951add5e2cd81%3A0x171e0b69c7c6f7ba!2sPasserelles%20num%C3%A9riques%20Cambodia%20(PNC)!5e0!3m2!1sen!2skh!4v1719050545804!5m2!1sen!2skh"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </div>

      <!-- Enhanced Success Modal -->
      <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
        <div class="bg-white p-8 rounded-2xl shadow-xl max-w-md w-full text-center transform transition-all duration-300 scale-0 animate-slideIn">
          <!-- Success Icon -->
          <div class="mb-4">
            <svg class="w-16 h-16 mx-auto text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-green-700 mb-2">Message Sent Successfully!</h3>
          <p class="text-gray-600 mb-6">Thank you, {{ lastSubmittedName }}! Your message has been sent, and we'll get back to you soon.</p>
          <button @click="showModal = false" class="bg-green-600 text-white px-6 py-3 rounded-full hover:bg-green-700 transition-all duration-200 transform hover:scale-105">
            Got It!
          </button>
        </div>
      </div>
    </div>
  </template>

  <script setup>
  import { reactive, ref, onMounted, onUnmounted } from 'vue'

  const form = reactive({
    name: '',
    email: '',
    message: ''
  })

  const showModal = ref(false)
  const lastSubmittedName = ref('')
  const currentSlide = ref(0)

  const slides = ref([
    {
      image: '/src/assets/img/banner4.png',
      caption: 'Connect with Us',
      description: 'Reach out for fresh fruits and great service!'
    },
    {
      image: '/src/assets/img/banner2.png',
      caption: 'Visit Our Farm',
      description: 'Explore where our fresh produce comes from.'
    },
    {
      image: '/src/assets/img/banner3.png',
      caption: 'Customer Support',
      description: 'We’re here to help with all your inquiries.'
    }
  ])

  function submitForm() {
    lastSubmittedName.value = form.name
    showModal.value = true
    form.name = ''
    form.email = ''
    form.message = ''
  }

  const nextSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % slides.value.length
  }

  const prevSlide = () => {
    currentSlide.value = (currentSlide.value - 1 + slides.value.length) % slides.value.length
  }

  const goToSlide = (index) => {
    currentSlide.value = index
  }

  // Auto-slide every 5 seconds
  let slideInterval = null
  onMounted(() => {
    slideInterval = setInterval(nextSlide, 5000)
  })

  onUnmounted(() => {
    clearInterval(slideInterval)
  })
  </script>

  <style>
  @keyframes slideIn {
    from {
      transform: translateY(-20px) scale(0.9);
      opacity: 0;
    }
    to {
      transform: translateY(0) scale(1);
      opacity: 1;
    }
  }

  .animate-slideIn {
    animation: slideIn 0.3s ease-out forwards;
  }
  </style>