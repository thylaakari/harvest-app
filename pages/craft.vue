<template>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center p-4"
  >
    <UCard class="w-full max-w-4xl bg-gray-800 border-gray-700 shadow-2xl">
      <template #header>
        <h1 class="text-3xl font-bold text-center text-amber-400 tracking-wide">
          Кузница Жатвы
        </h1>
        <p class="text-gray-400 text-center italic">
          Создавайте артефакты тёмной силы
        </p>
      </template>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 p-4">
        <UCard
          v-for="craft in crafts"
          :key="craft.id"
          class="bg-gray-700 border border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
        >
          <template #header>
            <h3 class="text-xl font-semibold text-amber-300">
              {{ craft.title }}
            </h3>
          </template>
          <div class="space-y-3">
            <h4 class="text-gray-300 font-medium">Компоненты:</h4>
            <ul class="list-none space-y-2">
              <li
                v-for="component in craft.components"
                :key="component"
                class="flex items-center gap-2 text-gray-200"
              >
                <UIcon name="i-heroicons-star" class="text-amber-400" />
                {{ component }}
              </li>
            </ul>
          </div>
        </UCard>
      </div>

      <template #footer>
        <div class="text-center py-4">
          <UButton
            to="/"
            variant="outline"
            size="lg"
            color="amber"
            class="hover:bg-added-600 hover:text-gray-100 transition-colors"
          >
            На главную
          </UButton>
        </div>
      </template>
    </UCard>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const crafts = ref([
  {
    id: 1,
    title: 'Зелье силы',
    components: ['2 воды', '1 изумруд'],
  },
  {
    id: 2,
    title: 'Железный щит',
    components: ['2 железа', '1 древесина'],
  },
  {
    id: 3,
    title: 'Изумрудный амулет',
    components: ['1 изумруд', '1 вода', '1 золото'],
  },
  {
    id: 4,
    title: 'Зелье скорости',
    components: ['1 вода', '1 изумруд', '1 древесина'],
  },
  {
    id: 5,
    title: 'Золотой клинок',
    components: ['2 железа', '1 золото'],
  },
  {
    id: 6,
    title: 'Эфирный факел',
    components: ['1 изумруд', '1 древесина', '1 вода'],
  },
  {
    id: 7,
    title: 'Зелье воскрешения',
    components: ['2 воды', '1 изумруд', '1 золото'],
  },
  {
    id: 8,
    title: 'Железные стрелы',
    components: ['1 железо', '1 древесина'],
  },
  {
    id: 9,
    title: 'Изумрудный ритуал',
    components: ['2 изумруда', '1 вода'],
  },
  {
    id: 10,
    title: 'Деревянный барьер',
    components: ['3 древесины'],
  },
  {
    id: 11,
    title: 'Железный голем',
    components: ['3 железа', '1 золото'],
  },
  {
    id: 12,
    title: 'Золотой алтарь',
    components: ['1 золото', '2 изумруда'],
  },
])
</script>

<style scoped>
/* Dark fantasy styling with mystical effects */
.bg-gray-900 {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url('https://source.unsplash.com/random/1920x1080?dark,fantasy,forge');
  background-size: cover;
  background-position: center;
}

/* Subtle glow effect on hover */
.bg-gray-700:hover {
  background-image: linear-gradient(
    rgba(251, 191, 36, 0.1),
    rgba(251, 191, 36, 0.1)
  );
}
</style>
