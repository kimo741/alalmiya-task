<template>
  <div class="section-card container">
    <!-- tite bar -->
    <div
      class="title_bar my-5 flex justify-between items-center h-[40px] w-full"
      v-if="title !== ''"
    >
      <div class="text-[20px] font-bold">
        {{ title }}
      </div>
      <div class="hidden sm:flex">
        <button class="" @click="preview">
          <!-- /////////////////////////// -->
          <!-- image in api has a problem -->
          <!-- ////////////////////////////// -->
          <img
            src="/public/images/card/arrow.png"
            alt=""
            class="reverse__arrow"
          />
        </button>
        <button class="mx-3" @click="next">
          <img src="/public/images/card/arrow.png" alt="" class="" />
        </button>
      </div>
    </div>
    <!-- <slot name="title"></slot> -->
    <div class="scroll_product row q-my-md">
      <!-- BTN TO SLIDE NEXT PRODUCT  -->

      <button
        @click="next"
        v-show="$viewport.isGreaterThan('mobile') && title === ''"
        class="hidden sm:block"
      >
        <svg
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 8 14"
          class="scroll_product-right w-6 h-6 text-gray-800 dark:text-white"
        >
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="m1 13 5.7-5.326a.909.909 0 0 0 0-1.348L1 1"
          />
        </svg>
      </button>

      <div class="row scroll_product-prod">
        <div
          style="transition: all 0.5s ease-in-out"
          :style="`transform:translateX(${scroll}px)`"
        >
          <div class="q-mx-sm scroll_product-prod__card full-height">
            <slot name="product"></slot>
          </div>
        </div>
      </div>
      <!-- BTN TO SLIDE PREVIEW PRODUCT  -->
      <button
        @click="preview"
        v-show="$viewport.isGreaterThan('mobile') && title === ''"
        class="hidden sm:block"
      >
        <svg
          class="scroll_product-left w-6 h-6 text-gray-800 dark:text-white"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 8 14"
        >
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M7 1 1.3 6.326a.91.91 0 0 0 0 1.348L7 13"
          />
        </svg>
      </button>
    </div>
  </div>
</template>
  
  <script setup>
const props = defineProps({
  title: {
    type: String,
    default: "",
  },
  cardCount: {
    type: Number,
  },
  cardSize: {
    type: Number,
  },
});
// state
const scroll = ref(0);
// methodth
const next = () => {
  console.log(window.innerWidth);
  var maxScroll;
  window.innerWidth > 1536
    ? (maxScroll = props.cardCount * props.cardSize - 1400)
    : window.innerWidth < 1536 && window.innerWidth > 1280
    ? (maxScroll = props.cardCount * props.cardSize - 1280)
    : window.innerWidth < 1280 && window.innerWidth > 1024
    ? (maxScroll = props.cardCount * props.cardSize - 1024)
    : window.innerWidth < 1280 && window.innerWidth > 768
    ? (maxScroll = props.cardCount * props.cardSize - 768)
    : (maxScroll = props.cardCount * props.cardSize);
  // : (maxScroll = props.cardCount * props.cardSize);
  //   console.log(window.innerWidth);
  if (scroll.value - props.cardSize >= -maxScroll) {
    scroll.value = scroll.value - props.cardSize;
    // console.log("max" + maxScroll);
    // console.log("scroll" + this.scroll);
  } else {
    scroll.value = -maxScroll;
  }
};
const preview = () => {
  //   console.log("preview");
  if (scroll.value >= 0 || scroll.value + props.cardSize >= 0) {
    scroll.value = 0;
  } else {
    scroll.value += props.cardSize;
  }
};
</script>
  
  <style lang="scss" scoped>
.section-card {
}
.scroll_product {
  position: relative;
  width: 100%;
  //   height: max-content;
  display: inline-block;
  flex-wrap: nowrap;
  overflow-x: auto;
  margin: auto;
  &::-webkit-scrollbar {
    width: 0 !important;
    height: 0 !important;
  }
  &-left,
  &-right {
    position: absolute;
    z-index: 100;
  }
  &-left {
    top: 50%;
    left: 0;
  }
  &-right {
    top: 50%;
    right: 0;
  }
  &-prod {
    display: block;
    top: 0;
    left: 5%;
    right: 5%;
    bottom: 0;
    flex-wrap: nowrap;
    white-space: nowrap;
    // overflow: hidden;
    &::-webkit-scrollbar {
      width: 0 !important;
    }
    &__card {
      display: inline-block;
      //   width: 300px;
      //   height: auto;
    }
  }
}
.see-more {
  position: absolute;
  top: 50% !important;
  left: 50%;
  .btn {
    margin: auto;
  }
}
.reverse__arrow {
  transform: rotate(180deg);
}
// #98978f
</style>