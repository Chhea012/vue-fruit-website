<template>
  <!-- Slideshow Section -->
  <section class=" bg-gray-100">
    <div class="w-full">
      <div class="relative">
        <!-- Slides -->
        <div class="overflow-hidden">
          <div class="flex transition-transform duration-500 ease-in-out" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
            <div v-for="(slide, index) in slides" :key="index" class="flex-shrink-0 w-full">
              <div class="relative">
                <img :src="slide.image" :alt="slide.caption" class="w-full h-[500px] object-cover  shadow-lg" />
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
  </section>
  <!-- Featured Products Section -->
  <section class="py-10 bg-gray-100">
    <div class="text-center mb-10">
      <h2 class="text-2xl md:text-3xl font-bold text-green-700">Featured Products</h2>
      <p class="text-gray-500">Items that you can't just miss</p>
    </div>

    <div class="max-w-7xl mx-auto grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8 px-6">
      <div
        v-for="product in products"
        :key="product.name"
        class="bg-white shadow-lg border border-gray-200 overflow-hidden hover:shadow-2xl transition duration-300 flex flex-col"
      >
        <!-- Image section with inner padding and border -->
        <div class="p-2">
          <div class="overflow-hidden h-72 border border-gray-300">
            <img
              :src="product.image"
              :alt="product.name"
              class="w-full h-full object-cover transform hover:scale-105 transition-transform duration-300"
            />
          </div>
        </div>

        <!-- Content section -->
        <div class="p-5 text-center flex flex-col flex-grow">
          <h3 class="text-lg font-semibold text-gray-800 mb-2">
            {{ product.name }}
          </h3>
          <p class="text-green-600 font-bold mb-4 text-base">${{ product.price }}</p>
          <button
            class="mt-auto px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700 text-sm"
          >
            {{ product.button }}
          </button>
        </div>
      </div>
    </div>
  </section>

  <!-- Banner Section -->
  <div class="bg-gray-200 py-10 px-4 text-center">
    <div class="max-w-5xl mx-auto flex flex-col lg:flex-row items-center justify-center gap-10">
      <!-- Fruits Image -->
      <div class="flex-shrink-0">
        <img
          src="/src/assets/img/banner.png"
          alt="Fruits"
          class="w-full max-w-md mx-auto"
        />
        <p class="mt-4 font-bold text-lg text-black">
          WWW.FruitSellCambodia.com
        </p>
      </div>

      <!-- Text Content -->
      <div class="text-left max-w-xl">
        <h1 class="text-4xl font-bold text-black">Healthy life</h1>
        <h2 class="text-3xl font-bold text-black mt-2">Happy perfect life</h2>
        <p class="text-gray-400 mt-2">
          From reversed forms around the world
        </p>
        <button
          class="mt-6 bg-green-500 text-white px-6 py-3 rounded-md text-lg hover:bg-green-600 transition"
        >
          Shop now
        </button>
      </div>
    </div>
  </div>

  <!-- Our Partner Section -->
  <section class="bg-gray-50 py-12">
    <div class="max-w-7xl mx-auto text-center px-6">
      <h2 class="text-lg md:text-xl font-semibold text-green-700 mb-4 uppercase tracking-wide">Our Partner</h2>

      <div class="bg-white rounded-xl shadow-md p-6 md:p-8 flex flex-wrap justify-center gap-12">
        <img src="/src/assets/collaboration/4.png" alt="E-GetS" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
        <img src="/src/assets/collaboration/2.png" alt="Grab" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
        <img src="/src/assets/collaboration/3.png" alt="FoodPanda" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
        <img src="/src/assets/collaboration/4.png" alt="TADA" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
        <img src="/src/assets/collaboration/5.png" alt="ABA Bank" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
        <img src="/src/assets/collaboration/image.png" alt="ACLEDA Bank" class="w-32 h-32 rounded-full object-contain transition-transform duration-300 hover:scale-110 hover:shadow-lg" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const products = [
  {
    name: "Cherry Tomatoes Fruit",
    price: 12,
    button: "Select options",
    image: "/src/assets/img/1.png",
  },
  {
    name: "Orange Fruit",
    price: 10,
    button: "Add to cost",
    image: "/src/assets/img/2.png",
  },
  {
    name: "Grapes Fruit",
    price: 12,
    button: "Add to cost",
    image: "/src/assets/img/3.png",
  },
  {
    name: "Watermelon Fruit",
    price: 12,
    button: "Add to cost",
    image: "/src/assets/img/4.png",
  },
  {
    name: "Strawberries Fruit",
    price: 12,
    button: "Add to cost",
    image: "/src/assets/img/5.png",
  },
  {
    name: "Bell peppers",
    price: 10,
    button: "Add to cost",
    image: "/src/assets/img/6.png",
  },
  {
    name: "Tulip flowers",
    price: 20,
    button: "Add to cost",
    image: "/src/assets/img/7.png",
  },
  {
    name: "Mango Fruit",
    price: 10,
    button: "Add to cost",
    image: "/src/assets/img/pp.png",
  },
]

const slides = ref([
  {
    image: '/src/assets/img/banner1.png',
    caption: 'Fresh Tropical Fruits',
    description: 'Explore our vibrant selection of tropical delights.'
  },
  {
    image: '/src/assets/img/banner2.png',
    caption: 'Organic Berries',
    description: 'Hand-picked berries for a healthy lifestyle.'
  },
  {
    image: '/src/assets/img/banner3.png',
    caption: 'Seasonal Specials',
    description: 'Discover the best of the season’s harvest.'
  }
])

const currentSlide = ref(0)

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