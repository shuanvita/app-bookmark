<script setup lang="ts">
import { onMounted, ref } from 'vue';
import { API_ROUTES } from './api';
import ProfileAvatar from './components/ProfileAvatar.vue';
import type { Profile } from './interfaces/profile';

const profile = ref<Profile>();

const fetchProfile = async () => {
  const data = await fetch(API_ROUTES.profile);
  const res = (await data.json()) as Profile;
  profile.value = res;
};

onMounted(() => {
  fetchProfile();
});
</script>

<template>
  <div class="flex gap-4 min-h-[calc(100vh-140px)] max-w-[1450px] mt-[140px] mx-auto">
    <nav class="min-w-[400px]">
      <ProfileAvatar v-if="profile" :name="profile.name" />
    </nav>
    <main>Контент</main>
  </div>
</template>
