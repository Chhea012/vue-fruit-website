<template>
    <div class="p-6 max-w-7xl mx-auto">
      <!-- Title -->
      <h1 class="text-3xl font-bold text-center mb-6">Trendy Food</h1>
  
      <!-- Filter Links -->
      <div class="flex justify-center gap-4 mb-6 font-semibold text-lg">
        <a href="#" class="text-green-600 border-b-2 border-green-600">All</a>
        <a href="#" class="hover:text-green-600">Featured</a>
        <a href="#" class="hover:text-green-600">New</a>
      </div>
  
      <!-- Product Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-2 justify-items-center">
        <ProductCard
          v-for="(item, index) in products"
          :key="index"
          :product="item"
        />
      </div>
    </div>
  </template>  
  
  <script setup>
  import ProductCard from './globals/ProductCard.vue';
  
  const products = [
    {
      name: 'Cabbage',
      image: '/src/assets/img/images/1.png',
      oldPrice: 8,
      newPrice: 6.5
    },
    {
      name: 'Cabbage',
      image: '/src/assets/img/images/2.png',
      oldPrice: 5,
      newPrice: 3.5
    },
    {
      name: 'Coquilles St',
      image: '/src/assets/img/images/3.png',
      oldPrice: 4,
      newPrice: 2
    },
    {
      name: 'Cabbage',
      image: '/src/assets/img/images/4.png',
      oldPrice: 5,
      newPrice: 2.5
    },
    {
      name: 'Beans',
      image: '/src/assets/img/images/5.png',
      oldPrice: 4,
      newPrice: 2.5
    },
    {
      name: 'Bitter melon',
      image: '/src/assets/img/images/6.png',
      oldPrice: 4,
      newPrice: 2.5
    },
    {
      name: 'Tralach vegetable',
      image: '/src/assets/img/images/7.png',
      oldPrice: 7,
      newPrice: 5.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/8.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/9.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/10.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/11.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/12.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/13.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/14.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/15.png',
      oldPrice: 6,
      newPrice: 4.5
    },
    {
      name: 'Pumpkins',
      image: '/src/assets/img/images/16.png',
      oldPrice: 6,
      newPrice: 4.5
    }
  ];
  </script>
  