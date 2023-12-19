<template>
  <div class="container my-[53px] w-full overflow-hidden">
    <div class="bannerTow flex flex-row h-[320px]">
      <!-- left section -->
      <div class="basis-1/2 bg-[#A092E0] rounded-[4px] relative">
        <div class="flex-col flex justify-center m-auto h-full p-[15%]">
          <div class="text-[32px] text-white font-bold z-10">
            Easier shopping with online fast delivery. Meet new feature!
          </div>
          <div>
            <button
              type="button"
              class="my-3 bg-white border border-[#FF4300] text-[#FF4300] hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
            >
              Learn More
            </button>
            <img src="/images/advertisement/banner1.png" class="img-bg" />
          </div>
        </div>
      </div>
      <!-- right section -->
      <div class="basis-1/2 bg-[#D5F07D] rounded-[4px] relative soc-section">
        <div
          class="flex-col flex justify-center items-center m-auto h-full p-[15%]"
        >
          <p class="text-[32px] text-black font-bold z-10">Seasonal offers</p>
          <button
            type="button"
            class="my-3 bg-[#FF4300] text-white hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
          >
            Shop Now
          </button>
        </div>
        <img
          src="/public/images/advertisement/strawberries.png"
          class="soc-section__img soc-section__img--1"
        />
        <img
          src="/public/images/advertisement/frots1.png"
          class="soc-section__img soc-section__img--2"
        />
        <img
          src="/public/images/advertisement/fruits2.png"
          class="soc-section__img soc-section__img--3"
        />
        <img
          src="/public/images/advertisement/fruits3.png"
          class="soc-section__img soc-section__img--4"
        />
        <img
          src="/public/images/advertisement/fruits3.png"
          class="soc-section__img soc-section__img--4"
        />
        <img
          src="/public/images/advertisement/fruits4.png"
          class="soc-section__img soc-section__img--5"
        />
        <img
          src="/public/images/advertisement/fruits5.png"
          class="soc-section__img soc-section__img--6"
        />
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style lang="scss">
.img-bg {
  position: absolute;
  height: 70%;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1;
}
.soc-section {
  &__img {
    position: absolute;
    &--1 {
      width: 242px;
      height: 161px;
      left: 0;
      top: 0;
    }
    &--2 {
      width: 163.335px;
      height: 267.549px;
      left: 0;
      bottom: 0;
    }
    &--3 {
      width: 165px;
      height: 224px;
      left: 20%;
      bottom: 0;
    }
    &--4 {
      width: 132px;
      height: 148px;
      right: 20%;
      bottom: 0;
    }
    &--5 {
      width: 248.924px;
      height: 213.364px;
      right: 0;
      top: 50%;
      transform: translateY(-50%);
    }
    &--6 {
      width: 254px;
      height: 154px;
      right: 20px;
      top: 0;
    }
  }
}
</style>