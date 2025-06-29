<template>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center p-4"
  >
    <UCard class="w-full max-w-4xl bg-gray-800 border-gray-700 shadow-2xl">
      <template #header>
        <h1 class="text-3xl font-bold text-center text-amber-400 tracking-wide">
          {{ race?.title || 'Раса не найдена' }}
        </h1>
        <p class="text-gray-400 text-center italic mt-2">
          {{ race?.subtitle || 'Описание отсутствует' }}
        </p>
      </template>

      <div class="p-6">
        <p class="text-lg text-gray-200 mb-6">
          {{ race?.description || 'Описание расы не найдено.' }}
        </p>
        <DataList :miniatures="race?.miniatures || []"></DataList>
      </div>

      <template #footer>
        <div class="text-center py-4">
          <UButton
            to="/"
            variant="outline"
            size="lg"
            color="amber"
            class="hover:bg-amber-600 hover:text-gray-100 transition-colors"
          >
            Назад к расам
          </UButton>
        </div>
      </template>
    </UCard>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { races } from '~/data/races'

const route = useRoute()
const slug = route.params.slug

// Поиск расы по slug
const race = ref(races[slug] || null)
</script>

<style scoped>
/* Тёмное фэнтези оформление с мистическими эффектами */
.bg-gray-900 {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url('https://source.unsplash.com/random/1920x1080?dark,fantasy');
  background-size: cover;
  background-position: center;
}
</style>
