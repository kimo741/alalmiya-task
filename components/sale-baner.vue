<template>
  <div class="container">
    <div
      class="sale-baner h-[200px] bg-[#007460] rounded-[8px] p-7 justify-between my-5 sm:flex hidden"
    >
      <div class="basis-1/2 flex flex-col justify-center px-3">
        <p class="text-white text-[24px] font-bold">
          Return up to 30% of the product cost by getting cashback on each
          order!
        </p>
        <div>
          <button
            type="button"
            class="my-3 bg-[#FF4300] text-white hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
          >
            Learn More
          </button>
        </div>
      </div>
      <div class="basis-1/2 flex justify-end relative">
        <img
          src="/images/advertisement/sale-baner.png"
          class="sale-baner__image"
        />
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style lang="scss">
.sale-baner__image {
  position: absolute;
}
</style>