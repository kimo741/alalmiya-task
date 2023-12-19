<template>
  <div flat class="my-card bg-card main-rounded">
    <!-- IMG FOR PRODUCT CARD -->
    <div class="img-card row justify-center items-center">
      <!-- <img :src="cardDetails.icon" /> -->
    </div>
    <div class="desc-card text-color text-center">
      <!-- TITLE FOR PRODUCT CARD -->
      <div class="header_card slider-title">
        <!-- {{ cardDetails.title }} -->sdsad
      </div>
      <!-- DESCRAPTION FOR PRODUCT CART -->
      <div class="slider-desc">cardDetails.description</div>
      <!-- BTN ACTION WILL EMIT PROCUCT WHEN CLICKED -->
    </div>
  </div>
</template>
  
  <script>
// import BtnAddToCart from "./BtnAddToCart.vue";
export default {
  props: ["cardDetails"],
  methods: {
    // addToCartAction() {
    //   this.$store.commit("cart/ADD_TO_CART", this.cardDetails);
    //   this.$emit("addToCartAction", this.cardDetails);
    // },
  },
  // components: { BtnAddToCart },
};
</script>
  
  <style lang="scss">
.my-card {
  display: inline-block;
  //   width: 100%;
  height: auto;
  margin: auto 30px;
  white-space: normal;
  //   transition: $main-transetion;
  text-overflow: ellipsis;
  // margin: 0 10px;
  scroll-snap-align: start;
  //   .btn__card-cart {
  //     @media (max-width: $breakpoint-sm-max) {
  //       opacity: 1 !important;
  //       transform: translate(0, 0) !important;
  //     }
  //   }

  &:hover {
    .btn__card-cart {
      opacity: 1;
      transform: translate(0, 0);
    }
    & {
      //   @media (min-width: $breakpoint-sm-max) {
      //     font-size: 0.8rem;
      //     transform: scale(1.03);
      //   }
      opacity: 0.9;
    }
  }
  .btn__card-cart:target {
    opacity: 1 !important;
    transform: translate(0, 0) !important;
  }

  // &:active {
  //   opacity: 1 !important;
  //   transform: translate(0, 0) !important;
  // }
}

.btn__card {
  &-cart {
    // width: 100%;
    opacity: 0;
    transform: translateY(100%);
    // transition: $main-transetion;
    // z-index: 10;
    border-radius: 8px;
  }
  &-heart {
    // z-index: 10;
    position: absolute;
    transform: translateX(-100%);
    left: 0;
    top: 10px;
    opacity: 0;
    // transition: $main-transetion;
  }
}
.img-card {
  height: 200px;
  //   width: 400px;
}
.desc-card {
  // white-space: nowrap;
  width: 400px;
  padding: 10px 15px;
  .text-caption {
    // text-overflow: ellipsis;
    width: 100%;
    // overflow: hidden;
  }
}
.slider-title {
  font-weight: 800;
  font-size: 16px;
  line-height: 24px;
  /* or 150% */

  text-align: center;
}
.slider-desc {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 24px;
  /* or 171% */

  text-align: center;

  color: #727272;
}
</style>