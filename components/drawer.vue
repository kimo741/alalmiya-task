<template>
  <!-- <div class="z-40 overflow-hidden"> -->
  <div
    :class="isOpen ? 'translate-x-0' : 'translate-x-[350px]'"
    class="fixed z-40 right-0 top-0 w-[300px] h-full overflow-hidden bg-white shadow-lg transform transition-transform duration-300 ease-in-out"
  >
    <div
      class="w-full text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-lg dark:bg-gray-700 dark:border-gray-600 dark:text-white"
    >
      <p class="w-full p-10 text-[20px] font-bold">Categorys</p>
      <a
        v-for="(category, i) in categories"
        :key="i"
        href="#"
        aria-current="true"
        class="block px-4 py-2 text-black w-full bg-gray-200 border-b border-gray-200 rounded-t-lg cursor-pointer"
      >
        {{ category.name }}
      </a>
    </div>
  </div>
  <div
    v-if="isOpen"
    @click="closeDrawer"
    class="fixed inset-0 bg-black opacity-50"
  ></div>
  <!-- </div> -->
</template>
  
  <script setup>
const categorys = ref([
  {
    name: "All Categorys",
  },
  { name: "Highest cashaback" },

  { name: "Top Deals" },
  { name: "Fruits & Vegetables" },
  { name: "Diary & Eggs" },
  { name: "Beverages & Drinks" },
  { name: "Fresh Bakery" },
  { name: "Baby Products" },
  { name: "Household" },
]);
const props = defineProps({
  isOpen: {
    type: Boolean,
  },
  categories: {
    type: Array,
  },
});
const emits = defineEmits(["closeDrawer"]);
const closeDrawer = () => {
  emits("closeDrawer");
};
</script>
  
  <style>
</style>