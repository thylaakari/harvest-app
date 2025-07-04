<template>
  <Navabar></Navabar>
  <div
    class="min-h-screen bg-gray-900 text-gray-100 flex flex-col items-center p-4 pt-20"
  >
    <NuxtPage></NuxtPage>
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
