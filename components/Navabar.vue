<template>
  <header
    class="bg-gray-900 text-gray-100 border-b border-gray-700 fixed top-0 left-0 right-0 z-50"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <h1 class="text-2xl font-bold text-amber-600">Жатва</h1>
        </div>

        <!-- Desktop Menu -->
        <nav class="hidden lg:flex space-x-4">
          <NuxtLink
            to="/"
            class="text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
          >
            Главная
          </NuxtLink>
          <NuxtLink
            to="/rules"
            class="text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
          >
            Правила
          </NuxtLink>
          <NuxtLink
            to="/craft"
            class="text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
          >
            Крафт
          </NuxtLink>
          <NuxtLink
            to="/game"
            class="text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
          >
            Начать игру
          </NuxtLink>
        </nav>

        <!-- Mobile Menu Button -->
        <div class="lg:hidden">
          <button
            @click="isOpen = !isOpen"
            class="text-amber-600 hover:text-amber-500 focus:outline-none"
            aria-label="Toggle mobile menu"
          >
            <svg
              v-if="!isOpen"
              class="h-6 w-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>
            <svg
              v-else
              class="h-6 w-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-if="isOpen" class="lg:hidden">
        <div class="bg-gray-800 px-4 pt-2 pb-3 space-y-1">
          <NuxtLink
            to="/"
            class="block text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
            @click="isOpen = false"
          >
            Главная
          </NuxtLink>
          <NuxtLink
            to="/rules"
            class="block text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
            @click="isOpen = false"
          >
            Правила
          </NuxtLink>
          <NuxtLink
            to="/craft"
            class="block text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
            @click="isOpen = false"
          >
            Крафт
          </NuxtLink>
          <NuxtLink
            to="/game"
            class="block text-gray-300 hover:text-amber-500 transition-colors px-3 py-2 rounded-md text-base font-medium"
            @click="isOpen = false"
          >
            Начать игру
          </NuxtLink>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
const isOpen = ref(false)
</script>
