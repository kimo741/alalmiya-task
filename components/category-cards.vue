<template>
  <div
    class="h-[150px] flex flex-col justify-between items-center w-full h-full"
  >
    <img
      :src="categorys_data?.image"
      alt="category image"
      class="w-[88px] h-[88px]"
    />
    <!-- categorys_data?.image -->
    <!-- {{ categorys_data?.image }} -->
    <p class="font-normal">{{ categorys_data?.name }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  categorys_data: {
    type: Object,
  },
});
</script>

<style>
</style>