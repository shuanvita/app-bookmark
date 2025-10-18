<script setup lang="ts">
import { useCategoriesStore } from '@/stores/categories.store';
import { onMounted } from 'vue';
import ButtonIcon from './ButtonIcon.vue';
import IconPlus from '@/icons/IconPlus.vue';

const store = useCategoriesStore();

onMounted(() => {
  store.fetchCategories();
});
</script>

<template>
  <ul class="flex flex-col gap-[34px]">
    <li v-for="category in store.categories" :key="category.id">
      <a
        class="text-[14px] hover:text-[24px] hover:font-bold duration-200"
        :href="`/${category.alias}`"
      >
        {{ category.name }}
      </a>
    </li>
    <li>
      <ButtonIcon @click="store.createCategory"><IconPlus /></ButtonIcon>
    </li>
  </ul>
</template>
