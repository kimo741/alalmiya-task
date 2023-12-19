<template>
  <div class="container">
    <div class="banner sm:block hidden">
      <div class="m-auto h-full flex-col flex justify-center items-center">
        <div class="banner__title">Flavours of Italy</div>
        <div class="banner__disc">
          20% off weekly offer for italian products
        </div>
        <button
          type="button"
          class="my-3 text-white bg-[#FF4300] hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
        >
          Shop Now
        </button>
      </div>
      <img
        src="/images/advertisement/product7.png"
        class="banner__imgs banner__imgs-img1"
      />
      <img
        src="/images/advertisement/product2.png"
        class="banner__imgs banner__imgs-img2"
      />
      <img
        src="/images/advertisement/product3.png"
        class="banner__imgs banner__imgs-img3"
      />
      <img
        src="/images/advertisement/product6.png"
        class="banner__imgs banner__imgs-img4"
      />
      <img
        src="/images/advertisement/product4.png"
        class="banner__imgs banner__imgs-img5"
      />
      <img
        src="/images/advertisement/product1.png"
        class="banner__imgs banner__imgs-img6"
      />
      <img
        src="/images/advertisement/product5.png"
        class="banner__imgs banner__imgs-img7"
      />
    </div>
    <div class="sm:hidden block w-full h-full p-[10px]">
      <img src="/images/card/mobile-baner.png" class="m-auto w-full h-full" />
    </div>
    <div class="sm:hidden block w-full h-full p-[10px]">
      <img
        src="/images/card/Delivery details.png"
        class="m-auto w-full h-full"
      />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.banner {
  position: relative;
  text-align: center;
  height: 400px;
  background-color: #00a9a2;
  border-radius: 8px;

  overflow: hidden;
  &__title {
    font-size: 56px;
    font-style: normal;
    color: white;
    z-index: 10;
  }
  &__disc {
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    color: white;
    z-index: 10;
  }
  &__imgs {
    position: absolute;
    z-index: 1;
    &-img1 {
      left: 20px;
      top: 10px;
      width: 144px;
      height: 196px;
    }
    &-img2 {
      left: 0px;
      bottom: 0;
      width: 200.132px;
      height: 300px;
    }
    &-img3 {
      left: 150px;
      bottom: 0;
      width: 224.5px;
      height: 278px;
    }
    &-img4 {
      right: 0;
      top: 10px;
      width: 256.231px;
      height: 306.131px;
      z-index: 2;
    }
    &-img5 {
      right: 200px;
      top: 0;
      width: 122.944px;
      height: 294.228px;
      z-index: 2;
    }
    &-img6 {
      right: 150px;
      bottom: 0;
      width: 119.582px;
      height: 182.628px;
      z-index: 1;
    }
    &-img7 {
      right: 300px;
      bottom: 0;
      width: 100px;
      height: 200px;
      z-index: 1;
    }
  }
}
</style>