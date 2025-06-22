<script setup>
import { RouterLink, RouterView, useRoute } from 'vue-router'

const route = useRoute()
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <!-- Navbar -->
    <nav class="bg-white shadow-md ">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0 text-2xl font-bold text-indigo-600">
            <RouterLink to="/">Fruit Shop</RouterLink>
          </div>

          <!-- Navigation Links -->
          <div class="hidden md:flex space-x-6">
            <RouterLink
              to="/"
              :class="route.path === '/' ? activeClass : linkClass"
            >
              Home
            </RouterLink>
            <RouterLink
              to="/about"
              :class="route.path === '/about' ? activeClass : linkClass"
            >
              About
            </RouterLink>
            <RouterLink
              to="/service"
              :class="route.path === '/service' ? activeClass : linkClass"
            >
              Service
            </RouterLink>
            <RouterLink
              to="/contact"
              :class="route.path === '/contact' ? activeClass : linkClass"
            >
              Contact
            </RouterLink>
          </div>
        </div>
      </div>
    </nav>

    <!-- Page Content -->
    <main class="flex-grow">
      <RouterView />
    </main>
  </div>

  <footer class="bg-green-900 text-gray-100 py-12">
  <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-8">

    <!-- Company Info -->
    <div>
      <h3 class="text-xl font-semibold mb-4">Company Name</h3>
      <p class="text-sm mb-4">Empowering businesses with smart partnerships and innovative solutions.</p>
      <div class="flex space-x-4 mt-4">
        <!-- Social Media Icons (example using Heroicons or SVGs) -->
        <a href="#" class="hover:text-white"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">...</svg></a>
        <a href="#" class="hover:text-white"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">...</svg></a>
        <a href="#" class="hover:text-white"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">...</svg></a>
      </div>
    </div>

    <!-- Quick Links -->
    <div>
      <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
      <ul class="space-y-2 text-sm">
        <li><a href="#" class="hover:underline">Home</a></li>
        <li><a href="#" class="hover:underline">About Us</a></li>
        <li><a href="#" class="hover:underline">Services</a></li>
        <li><a href="#" class="hover:underline">Partners</a></li>
        <li><a href="#" class="hover:underline">Contact</a></li>
      </ul>
    </div>

    <!-- Support -->
    <div>
      <h4 class="text-lg font-semibold mb-4">Support</h4>
      <ul class="space-y-2 text-sm">
        <li><a href="#" class="hover:underline">Help Center</a></li>
        <li><a href="#" class="hover:underline">Terms of Service</a></li>
        <li><a href="#" class="hover:underline">Privacy Policy</a></li>
        <li><a href="#" class="hover:underline">Accessibility</a></li>
      </ul>
    </div>

    <!-- Newsletter -->
    <div>
      <h4 class="text-lg font-semibold mb-4">Subscribe</h4>
      <p class="text-sm mb-4">Get updates on new features and offers.</p>
      <form class="flex flex-col sm:flex-row items-center gap-2">
        <input type="email" placeholder="Email address" class="w-full px-4 py-2 rounded-md text-gray-800 focus:outline-none" />
        <button class="bg-green-600 hover:bg-green-500 px-4 py-2 rounded-md text-white">Subscribe</button>
      </form>
    </div>
  </div>

  <div class="text-center text-sm text-gray-400 mt-10">
    &copy; 2025 Company Name. All rights reserved.
  </div>
</footer>

</template>

<script>
const linkClass =
  'text-gray-600 hover:text-indigo-600 transition-colors duration-300 font-medium'
const activeClass =
  'text-indigo-600 font-semibold border-b-2 border-indigo-600 pb-1'
</script>