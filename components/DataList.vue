<template>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center p-4"
  >
    <UCard class="w-full max-w-4xl bg-gray-800 border-gray-700 shadow-2xl">
      <template #header>
        <h2 class="text-3xl font-bold text-center text-amber-400 tracking-wide">
          Миниатюры Жатвы
        </h2>
        <p class="text-gray-400 text-center italic">Воплощения силы и хаоса</p>
      </template>

      <div
        v-if="miniatures && miniatures.length"
        class="grid grid-cols-1 gap-6 p-6"
      >
        <UCard
          v-for="miniature in miniatures"
          :key="miniature.id"
          class="bg-gray-700 border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
        >
          <template #header>
            <h3 class="text-xl font-semibold text-amber-300">
              {{ miniature.name }}
            </h3>
          </template>
          <div class="p-4">
            <table
              v-if="hasValidStats(miniature)"
              class="w-full mt-4 text-gray-200 border-collapse"
            >
              <thead>
                <tr class="bg-amber-900/20">
                  <th class="p-2 border-b border-amber-400/10">ОЗ</th>
                  <th class="p-2 border-b border-amber-400/10">Ск</th>
                  <th class="p-2 border-b border-amber-400/10">ББ</th>
                  <th class="p-2 border-b border-amber-400/10">ДБ</th>
                  <th class="p-2 border-b border-amber-400/10">З</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="p-2 text-center border-b border-amber-400/10">
                    {{ miniature.health ?? '–' }}
                  </td>
                  <td class="p-2 text-center border-b border-amber-400/10">
                    {{ miniature.speed ?? '–' }}
                  </td>
                  <td class="p-2 text-center border-b border-amber-400/10">
                    {{ miniature.attack ?? '–' }}
                  </td>
                  <td class="p-2 text-center border-b border-amber-400/10">
                    {{ miniature.strike ?? '–' }}
                  </td>
                  <td class="p-2 text-center border-b border-amber-400/10">
                    {{ miniature.defense ?? '–' }}
                  </td>
                </tr>
              </tbody>
            </table>
            <p v-else class="text-gray-400 italic">
              Нет данных о характеристиках...
            </p>
            <p class="font-semibold mt-4 text-amber-300">Способности:</p>
            <ul class="list-none space-y-2 mt-2">
              <li
                v-for="(skill, index) in miniature.skills || []"
                :key="index"
                class="flex items-center gap-2 text-gray-200"
              >
                <UIcon name="i-heroicons-star" class="text-amber-400" />
                {{ skill || 'Нет способностей' }}
              </li>
            </ul>
          </div>
        </UCard>
      </div>
      <p v-else class="text-gray-400 italic text-center p-6">
        Миниатюры отсутствуют...
      </p>

      <template #footer>
        <div class="text-center py-4">
          <UButton
            to="/"
            variant="outline"
            size="lg"
            color="amber"
            class="hover:bg-amber-600 hover:text-gray-100 transition-colors"
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

defineProps({
  miniatures: {
    type: Array,
    required: true,
  },
})

// Проверка валидности характеристик миниатюры
const hasValidStats = (miniature) => {
  return (
    miniature &&
    (miniature.health != null ||
      miniature.speed != null ||
      miniature.attack != null ||
      miniature.strike != null ||
      miniature.defense != null)
  )
}
</script>

<style scoped>
/* Тёмное фэнтези оформление с мистическими эффектами */
.bg-gray-900 {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url('https://source.unsplash.com/random/1920x1080?dark,fantasy,battle');
  background-size: cover;
  background-position: center;
}

/* Эффект свечения при наведении */
.bg-gray-700:hover {
  background-image: linear-gradient(
    rgba(251, 191, 36, 0.1),
    rgba(251, 191, 36, 0.1)
  );
}
</style>
