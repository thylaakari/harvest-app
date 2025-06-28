<template>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center p-4"
  >
    <UCard class="w-full max-w-4xl bg-gray-800 border-gray-700 shadow-2xl">
      <!-- Header Section -->
      <header class="text-center py-8">
        <h1 class="text-4xl font-bold text-amber-400 tracking-wide">Жатва</h1>
        <p class="text-lg text-gray-300 italic mt-2">
          Темное фэнтези сражения за ресурсы и флаги
        </p>
      </header>

      <!-- Races Section -->
      <section class="p-6">
        <h2 class="text-2xl font-semibold text-amber-300 text-center mb-6">
          Расы
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <NuxtLink to="/terranthropes">
            <UCard
              class="bg-gray-700 border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
            >
              <div class="p-4">
                <h3 class="text-xl font-semibold text-amber-300">
                  Террантропы
                </h3>
              </div>
            </UCard>
          </NuxtLink>
          <NuxtLink to="/strikes">
            <UCard
              class="bg-gray-700 border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
            >
              <div class="p-4">
                <h3 class="text-xl font-semibold text-amber-300">
                  Пепельные стрелки
                </h3>
              </div>
            </UCard>
          </NuxtLink>
          <NuxtLink to="/clans">
            <UCard
              class="bg-gray-700 border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
            >
              <div class="p-4">
                <h3 class="text-xl font-semibold text-amber-300">
                  Костяные кланы
                </h3>
              </div>
            </UCard>
          </NuxtLink>
          <NuxtLink to="/demons">
            <UCard
              class="bg-gray-700 border-gray-600 hover:shadow-[0_0_15px_rgba(251,191,36,0.5)] transition-all duration-300 transform hover:-translate-y-1"
            >
              <div class="p-4">
                <h3 class="text-xl font-semibold text-amber-300">
                  Порождения бездны
                </h3>
              </div>
            </UCard>
          </NuxtLink>
        </div>
      </section>

      <!-- Action Buttons -->
      <section class="py-12 text-center space-y-6">
        <UButton
          to="/game"
          variant="solid"
          size="xl"
          color="amber"
          class="hover:bg-amber-600 transition-colors"
        >
          Начать игру
        </UButton>
        <UButton
          to="/craft"
          variant="solid"
          size="xl"
          color="amber"
          class="hover:bg-amber-600 transition-colors"
        >
          Крафт
        </UButton>
      </section>
    </UCard>
  </div>
</template>

<script setup></script>

<style scoped>
/* Dark fantasy styling with mystical effects */
.bg-gray-900 {
  background-image:
    linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url('https://source.unsplash.com/random/1920x1080?dark,fantasy');
  background-size: cover;
  background-position: center;
}

/* Subtle glow effect on hover for cards */
.bg-gray-700:hover {
  background-image: linear-gradient(
    rgba(251, 191, 36, 0.1),
    rgba(251, 191, 36, 0.1)
  );
}
</style>
