<template>
  <div
    class="w-full fixed bottom-0 left-0 h-[70px] flex justify-evenly items-center bg-white"
  >
    <div
      class="flex flex-col justify-between items-center"
      v-for="(link, i) in routerIcons"
      :key="i"
    >
      <div><img :src="link.img" /></div>
      <p class="text-[7px]">{{ link.name }}</p>
    </div>
  </div>
</template>

<script setup>
const routerIcons = [
  { name: "Home", img: "/images/icons/Home.png", to: "/" },
  {
    name: "Categories",
    img: "/images/icons/dashboard-square.png",
    to: "/categories",
  },
  { name: "Deals", img: "/images/icons/discount-tag.png", to: "/deals" },
  { name: "Cart", img: "/images/icons/shopping-cart.png", to: "/Cart" },
  { name: "Account", img: "/images/icons/user.png", to: "/Account" },
];
</script>

<style>
</style>