<script setup lang="ts">
import { useProfileStore } from '@/stores/profile.store';
import { onMounted } from 'vue';

const store = useProfileStore();

onMounted(() => {
  store.fetchProfile();
});
</script>

<template>
  <div class="flex flex-col gap-6" v-if="store.profile">
    <img class="self-start" src="/avatar.png" alt="Avatar" />
    <div class="text-[18px] tracking-[0.36px]">
      Привет, <strong>{{ store.profile.name }}</strong>
    </div>
  </div>
</template>
