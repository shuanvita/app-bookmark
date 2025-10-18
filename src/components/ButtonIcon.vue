<script setup lang="ts">
const { size = 32 } = defineProps<{ size?: number }>();
</script>

<template>
  <button
    class="flex items-center justify-center bg-foreground cursor-pointer rounded-full"
    :style="{ width: `${size}px`, height: `${size}px` }"
  >
    <slot />
  </button>
</template>
