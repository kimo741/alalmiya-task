<template>
  <div class="footer bg-[#272727] sm:h-[380px] h-[704px];">
    <div class="container">
      <div
        class="flex justify-between sm:h-[320px] h-[550px] flex-wrap sm:flex-nowrap"
      >
        <div
          class="sm:basis-2/12 w-full flex flex-col justify-evenly items-center"
        >
          <div class="w-full sm:b-0 p-5">
            <img src="/public/images/logo2.png" class="w-[174px] h-[52px]" />
          </div>
          <div class="w-full">
            <p class="text-[13px] sm:b-0 px-5 pb-5 text-[#ffffff6f]">
              Follow us
            </p>
            <div class="flex justify-evenly w-full">
              <div v-for="(link, i) in socialLinks" :key="i">
                <img :src="link" class="w-[24px] h-[24px]" />
              </div>
            </div>
          </div>
          <div></div>
        </div>
        <!-- About Company list -->
        <div class="sm:basis-2/12 basis-6/12 flex flex-col sm:px-0 px-5">
          <p class="text-[#ffffff6f] mt-10 mb-3 text-[13px]">About Company</p>
          <p
            class="text-white mb-5 cursor-pointer text-[15px]"
            v-for="(item, i) in aboutCompany"
            :key="i"
          >
            {{ item }}
          </p>
        </div>
        <!-- Customer support -->
        <div class="sm:basis-2/12 basis-6/12 flex flex-col sm:px-0 px-5">
          <p class="text-[#ffffff6f] mt-10 mb-3 text-[13px]">
            Customer support
          </p>
          <p
            class="text-white mb-5 cursor-pointer text-[15px]"
            v-for="(item, i) in customerSupport"
            :key="i"
          >
            {{ item }}
          </p>
        </div>
        <!-- Services -->
        <div class="sm:basis-2/12 basis-6/12 flex flex-col sm:px-0 px-5">
          <p class="text-[#ffffff6f] mt-10 mb-3 text-[13px]">Services</p>
          <p
            class="text-white mb-5 cursor-pointer text-[15px]"
            v-for="(item, i) in services"
            :key="i"
          >
            {{ item }}
          </p>
        </div>
        <!-- Our programs -->
        <div class="sm:basis-2/12 basis-6/12 flex flex-col sm:px-0 px-5">
          <p class="text-[#ffffff6f] mt-10 mb-3 text-[13px]">Our programs</p>
          <p
            class="text-white mb-5 cursor-pointer text-[15px]"
            v-for="(item, i) in ourPrograms"
            :key="i"
          >
            {{ item }}
          </p>
        </div>
        <div class="basis-2/12 sm:flex hidden flex-col">
          <p class="text-[#ffffff6f] mt-10 mb-3">
            <span class="text-[#ffffff6f] text-[15px] cursor-pointer">AR </span>
            <span class="text-white cursor-pointer">| EN</span>
          </p>
          <p class="text-[#ffffff6f] mt-10 mb-3 text-[12px]">
            Avaliable paument methods
          </p>
          <div class="mb-3">
            <img
              src="/public/images/social/paymentM.png"
              class="cursor-pointer"
            />
          </div>
          <div class="flex justify-center items-center">
            <img
              src="/public/images/social/mada.png"
              class="mx-5 cursor-pointer"
            />
            <img
              src="/public/images/social/cash.png"
              class="mx-5 cursor-pointer"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const socialLinks = [
  "/images/social/Facebook.png",
  "/images/social/_Instagram.png",
  "/images/social/Twitter Logo.png",
  "/images/social/snap.png",
  "/images/social/youtube.png",
  "/images/social/_TikTok.png",
];
const aboutCompany = [
  "About Us",
  "News",
  "Store locations",
  "Careers",
  "Sell with us",
];
const customerSupport = ["Contact Us", "Returns & Exchanges", "Privacy Policy"];
const services = [
  "Services & Warranty",
  "Terms & Conditions",
  "Shipping & Delivery ",
];
const ourPrograms = ["Cashback programs", "Gift Cards", "Weekly Offers"];
</script>

<style>
</style>