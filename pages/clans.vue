<template>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center"
  >
    <UCard class="w-full max-w-4xl bg-gray-800 border-gray-700 shadow-2xl">
      <template #header>
        <h1 class="text-3xl font-bold text-center text-amber-400 tracking-wide">
          Костяные кланы
        </h1>
      </template>

      <div>
        <p class="text-lg text-gray-200 mb-6">
          Воины, связанные с некромантией и магией костей. Они оживляют павших и
          усиливают союзников, сосредотачиваясь на выживании и контроле зон
          через прочные миниатюры и способности восстановления.
        </p>

        <DataList :miniatures="miniatures"></DataList>
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
// Sample miniatures data for Terranthropes
const miniatures = ref([
  {
    id: 8,
    name: 'Кованый страж',
    health: 5,
    attack: 3,
    strike: '-',
    defense: 4,
    speed: 4,
    skills: [
      'Костяной щит: за 2 ПО создаёт барьер в своей зоне, защищающий одну союзную миниатюру от потери ПО или ресурсов до конца раунда',
      'Непробиваемая броня: получает +1 к защите, если находится в зоне захвата флага',
    ],
  },
  {
    id: 9,
    name: 'Костяной берсерк',
    health: 4,
    attack: 3,
    strike: '-',
    defense: 2,
    speed: 5,
    skills: [
      'Ярость костей: за 2 ПО атакует одну вражескую миниатюру в той же зоне, нанося 1 урона и заставляя её потерять 1 ПО',
      'Кровавая жатва: получает +1 ПО, если уничтожает вражескую миниатюру в бою',
    ],
  },
  {
    id: 10,
    name: 'Костяной жнец',
    health: 4,
    attack: 2,
    strike: '-',
    defense: 3,
    speed: 6,
    skills: [
      'Жатва душ: за 2 ПО атакует всех врагов в своей зоне, заставляя каждую потерять 1 ПО',
      'Тень смерти: при перемещении в зону добычи получает +1 ресурс',
    ],
  },
  {
    id: 11,
    name: 'Могильный копейщик',
    health: 8,
    attack: 3,
    strike: '3, дистанция 3',
    defense: 3,
    speed: 3,
    skills: [
      'Проклятое копьё: за 2 ПО наносит 4 урона одной вражеской миниатюре в зоне до 3 клеток, снижая её защиту на 1 до конца раунда',
      'Страж могил: союзные миниатюры в той же зоне захвата флага получают +1 ПО',
    ],
  },
  {
    id: 12,
    name: 'Черепной вождь',
    health: 16,
    attack: 6,
    strike: '-',
    defense: 6,
    speed: 7,
    skills: [
      'Клич мертвецов: за 3 ПО все союзные миниатюры в той же зоне получают +1 ПО в этом раунде',
      'Костяное величие: вражеские миниатюры в той же зоне не могут собирать ресурсы',
    ],
  },
])
</script>
