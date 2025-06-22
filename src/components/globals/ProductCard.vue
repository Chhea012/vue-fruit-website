<template>
    <div class="w-48 text-center">
      <div class="relative border border-green-600 overflow-hidden rounded-tr-2xl rounded-bl-2xl bg-white">
        <!-- Badge -->
        <div class="absolute top-0 left-0 bg-green-700 text-white text-sm px-2 py-0.5 rounded-br-lg z-10">
          New
        </div>
  
        <!-- Image (full, not cropped) -->
        <img
          :src="product.image"
          alt="vegetable"
          class="w-full h-48 object-contain p-2 rounded-tr-2xl rounded-bl-2xl"
        />
      </div>
  
      <!-- Title -->
      <h2 class="mt-2 font-bold text-lg text-black">{{ product.name }}</h2>
  
      <!-- Prices -->
      <div class="text-base mt-1">
        <span class="text-red-600 font-semibold line-through mr-1">
          ${{ product.oldPrice }}
        </span>
        <span class="text-green-600 font-bold">${{ product.newPrice }}</span>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    product: {
      type: Object,
      required: true
    }
  });
  </script>
  