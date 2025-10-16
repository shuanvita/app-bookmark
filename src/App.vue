<script setup lang="ts">
import ProfileAvatar from './components/ProfileAvatar.vue';
</script>

<template>
  <div class="flex gap-4 min-h-[calc(100vh-140px)] max-w-[1450px] mt-[140px] mx-auto">
    <nav class="min-w-[400px]">
      <ProfileAvatar />
    </nav>
    <main>Контент</main>
  </div>
</template>
