<template>
    <div class="bg-gray-100 min-h-screen py-12 px-4 sm:px-6 lg:px-8">
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
  import { reactive, ref } from 'vue';
  
  const form = reactive({
    name: '',
    email: '',
    message: ''
  });
  
  const showModal = ref(false);
  const lastSubmittedName = ref('');
  
  function submitForm() {
    lastSubmittedName.value = form.name;
    showModal.value = true;
    form.name = '';
    form.email = '';
    form.message = '';
  }
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