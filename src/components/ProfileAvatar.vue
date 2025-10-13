<script setup lang="ts">
const { name } = defineProps<{ name: string }>();
</script>

<template>
  <div class="flex flex-col gap-6">
    <img class="self-start" src="/avatar.png" alt="Avatar" />
    <div class="text-[18px] tracking-[0.36px]">
      Привет, <strong>{{ name }}</strong>
    </div>
  </div>
</template>
