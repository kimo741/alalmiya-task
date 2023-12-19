<template>
  <div class="category-bar bg-white">
    <div class="container py-3">
      <div class="flex justify-between text-xs font-bold">
        <div
          v-for="(category, index) in categorys"
          :key="index"
          class="cursor-pointer"
          style="
             {
              width: calc(94% / categorys.length);
            }
          "
        >
          {{ category.name }}
        </div>
      </div>
    </div>
  </div>
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
</script>

<style>
.category-bar {
  height: 52px;
  position: relative;
}
.category-bar::after {
  content: "";
  position: absolute;
  bottom: 10px;
  height: 1px;
  width: 100%;
  background: #b0b0b0;
}
</style>