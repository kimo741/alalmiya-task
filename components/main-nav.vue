<template>
  <nav class="bg-white hidden sm:block">
    <div class="container items-center flex gap-x-5 main-nav">
      <!-- logo -->
      <div class="basis-2/12">
        <img class="h-full" src="/images/logo.png" />
      </div>
      <!-- search bar -->
      <search-inputs class="basis-3/12" />
      <!-- location -->
      <div class="basis-3/12 flex my-auto">
        <img class="w-8 h-8 m-auto" src="/images/top-nav/location.png" />
        <div class="basis-3/6 text-xs">
          <p class="text-gray-500">Delivery To:</p>
          <p>Sulaimaniyah Dist, 455 Riyad Saud...(30-45 mins)</p>
        </div>
        <a class="m-auto underline text-orange-500 cursor-pointer">Change</a>
      </div>
      <!-- cashback -->
      <div class="basis-2/12">
        <div class="py-1 px-4 rounded-b-lg bg-yellow-200 w-9/12">
          <p class="text-xs">Your Cashback</p>
          <div class="flex">
            <img class="w-5 h-5" src="/public/images/top-nav/wallet.png" />
            <b class="text-xs font-bold">SAR 124,00</b>
          </div>
        </div>
      </div>
      <div class="basis-2/12">
        <div class="flex justify-between h-full items-center">
          <img
            class="cursor-pointer w-5 h-5"
            src="/images/top-nav/Notification.png"
          />
          <img class="cursor-pointer w-5 h-5" src="/images/top-nav/user.png" />
          <img
            class="cursor-pointer w-5 h-5"
            src="/images/top-nav/Favourite.png"
          />
          <img class="cursor-pointer w-5 h-5" src="/images/top-nav/Cart.png" />
        </div>
      </div>
    </div>
  </nav>
  <!-- mobile view -->
  <div
    class="sm:hidden flex h-[158px] w-full bg-[#007460] flex-col p-10 justify-evenly"
  >
    <div class="flex w-full justify-between basis-1/2">
      <div class="basis-1/2 flex justify-between">
        <button @click="toggleDrawer">
          <img src="/images/menu-line.png" />
        </button>
        <div><img src="/images/logo2.png" class="h-[32px] w-[106px]" /></div>
      </div>
      <div class="basis-1/2 flex justify-end">
        <div
          class="flex items-center rounded-br-lg bg-yellow-200 h-[24px] w-[90px] px-1 mr-5"
        >
          <img class="w-4 h-4" src="/public/images/top-nav/wallet.png" />
          <div class="text-center h-full">
            <span class="text-[9px] m-auto text-center h-full font-bold"
              >+52.99
            </span>
            <span class="text-[8px] m-auto h-full">SAR</span>
          </div>
        </div>
        <div>
          <img
            class="cursor-pointer w-5 h-5"
            src="/images/top-nav/Cart-white.png"
          />
        </div>
      </div>
      <!-- <div class="basis-1/2"></div> -->
    </div>
    <div class="flex justify-between">
      <search-inputs class="w-[80%]" />
      <div class="">
        <img src="/images/top-nav/Notification-white.png" />
      </div>
    </div>
  </div>
</template>

<script setup>
import searchInputs from "./inputs/search-inputs.vue";
const emit = defineEmits(["toggleDrawer"]);
const toggleDrawer = () => {
  emit("toggleDrawer");
};
</script>

<style>
.main-nav {
  height: 72px;
}
</style>