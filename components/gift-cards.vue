<template>
  <div class="container h-[432px] bg-[#D5F07D] relative hidden sm:block">
    <div class="flex flex-col justify-center p-[32px] w-[50%] h-full z-10">
      <div class="text-[35px] mb-[32px] font-bold">
        Take care just like that with Dukan gift cards
      </div>
      <div>
        <button
          type="button"
          class="my-3 bg-[#007460] text-white hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
        >
          Learn More
        </button>
      </div>
    </div>
    <img
      src="/images/advertisement/gift-card1.png"
      class="gift__img gift__img-1"
    />
    <img
      src="/images/advertisement/gift-card2.png"
      class="gift__img gift__img-2"
    />
    <img
      src="/images/advertisement/gift-card3.png"
      class="gift__img gift__img-3"
    />
    <div class="gift__desc text-[14px]">
      Some explanation small text if needed displayed here. Lorem ipsum dolor
      sit amet, consectetur adipiscing elit. Donec lobortis egestas mi
    </div>
  </div>
  <div class="gap-4 grid-cols-2 sm:hidden block">
    <div><img src="/images/card/soda-drink.png" /></div>
    <div><img src="/images/card/cakes.png" /></div>
    <div><img src="/images/card/fresh.png" /></div>
    <div><img src="/images/card/pasta.png" /></div>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
.gift__img {
  position: absolute;
  width: 320px;
  height: 193px;
  &-1 {
    right: 300px;
    top: 0px;
  }
  &-2 {
    right: 0;
    top: 48px;
  }
  &-3 {
    right: 150px;
    bottom: 0;
  }
}
.gift__desc {
  position: absolute;
  width: 50%;
  left: 35px;
  bottom: 35px;
}
</style>