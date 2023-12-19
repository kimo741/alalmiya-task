<template>
  <div class="product-card w-[295px] h-[452px] flex flex-col">
    <!-- top card -->
    <div class="flex justify-between bg-transparent h-[32px]">
      <!-- /////////// -->
      <!-- if has a sale -->
      <!-- /////////// -->
      <div
        v-if="product.have_sale"
        class="w-[68px] h-[20px] rounded-b-[8px] text-white text-center"
      >
        <span>Sale </span> <span>{{ Math.trunc(product.percentage) }}%</span>
      </div>
      <!-- else -->
      <img
        v-else
        src="/images/card/fire-fill 2.png"
        class="w-[68px] h-[20px]"
      />
      <buton
        @click="addToFavorits"
        v-if="!product.is_fav"
        class="w-[30px] h-[30px]"
      >
        <img src="/images/card/unfavourite.png" class="w-[30px] h-[30px]" />
      </buton>
      <buton @click="removeFromFavorits" v-else class="w-[30px] h-[30px]">
        <img src="/images/card/favourite.png" class="w-[30px] h-[30px]" />
      </buton>
    </div>
    <!-- card image -->
    <div
      class="text-center w-full h-[220px] flex justify-center items-center relative bg-white"
    >
      <img
        src="/images/card/image Frame.png"
        class="w-[220px] h-full m-auto product_image"
      />
    </div>
    <!-- count in cart  -->
    <div class="h-[40px] flex justify-between items-center w-full">
      <div
        @click="addToCart"
        class="w-[40px] text-center bg-[#007460] h-[40px] rounded-[8px] text-[25px] cursor-pointer text-white"
      >
        +
      </div>
      <div
        v-show="product.in_cart_count"
        class="text-center text-[16px] font-bold"
      >
        {{ product.in_cart_count }}
      </div>
      <div
        @click="removeFromCart"
        v-show="product.in_cart_count"
        class="w-[40px] text-center bg-[#007460] h-[40px] rounded-[8px] text-[25px] cursor-pointer text-white"
      >
        -
      </div>
    </div>
    <!-- rating & cach back & list -->
    <div class="flex justify-between items-center h-[28px]">
      <div>
        <RateProduct :rate="product?.rate_avg" />
      </div>
      <div class="">
        <div
          class="flex justify-between items-center h-[20px] bg-[#F7DE6F] p-3 rounded-b-[8px]"
        >
          <img src="/images/top-nav/wallet.png" class="h-[16px] w-[16px]" />
          <p class="text-center">
            <span class="text-[16px]">+5.99</span>
            <span class="text-[12px]">SAR</span>
          </p>
        </div>
      </div>
      <div>
        <img src="/images/card/list_add_check.png" class="h-[32px] w-[32px]" />
      </div>
    </div>
    <!-- price -->
    <div class="flex flex-col h-[100px]">
      <div v-if="!product.available_quantity" class="text-[#FF4300]">
        <span class="text-[20px]">Out of stock </span>
      </div>
      <div v-else class="text-[#FF4300]">
        <span class="text-[20px]"
          >{{
            product.price_after
              ? Number(product.price_after).toFixed(2)
              : Number(product?.price).toFixed(2)
          }}
        </span>
        <span class="text-[14px]">{{ product?.currency }}</span>
      </div>
      <!-- if out of stock -->

      <!-- ///// -->
      <!-- old price -->
      <!-- if has a sale -->
      <div v-if="product.percentage" class="text-[#B0B0B0] line-through">
        <span class="text-[20px]"
          >{{ Number(product?.price).toFixed(2) }}
        </span>
        <span class="text-[14px]">{{ product?.currency }}</span>
      </div>
      <div class="text-[16px] text-black">
        {{ product.name }}
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  product: {
    type: Object,
  },
  productType: {
    type: String,
  },
});
const emits = defineEmits([
  "addToFavorts",
  "removeFromFavorits",
  "incrementCountToCart",
  "decrementCountFromCart",
]);
import RateProduct from "./rate-product.vue";
const storage = ref(null);
const addToFavorits = () => {
  return emits("addToFavorts", {
    productId: props.product.id,
    propAction: "is_fav",
    addOrRemove: true,
    type: props.productType,
  });
};
const removeFromFavorits = () => {
  return emits("removeFromFavorits", {
    productId: props.product.id,
    propAction: "is_fav",
    addOrRemove: false,
    type: props.productType,
  });
};
const addToCart = () => {
  return emits("incrementCountToCart", {
    productId: props.product.id,
    propAction: "product_id_in_cart",
    addOrRemove: true,
    type: props.productType,
  });
};
const removeFromCart = () => {
  props.product.in_cart_count > 0
    ? emits("decrementCountFromCart", {
        productId: props.product.id,
        propAction: "product_id_in_cart",
        addOrRemove: false,
        type: props.productType,
      })
    : "";
};
</script>

<style>
.product_image {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
</style>