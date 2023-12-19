<template>
  <div class="w-full overflow-hidden">
    <top-nav class="hidden sm:block" />
    <main-nav class="hidden sm:block" @toggleDrawer="toggleDrawer" />
    <drawer
      class="z-200"
      :isOpen="isOpenDrawer"
      @closeDrawer="isOpenDrawer = !isOpenDrawer"
      :categories="categorys_data?.data"
    >
      <template></template>
    </drawer>
    <categorys-bar class="hidden sm:block" />
    <!-- mobile nav -->
    <!-- ////////// -->
    <!-- //////////// -->
    <baner />
    <banner-tow-sections class="hidden sm:block" />
    <!-- /////////////// -->
    <!-- category slider -->
    <!-- /////////////// -->
    <slider-container :cardCount="categorys_data?.data.length" :cardSize="90">
      <template #product>
        <div
          class="cards slide-items w-[90px] h-[90px] ml-[10px]"
          v-for="(cat, index) in categorys_data?.data"
          :key="index"
        >
          <category-cards :categorys_data="cat" />
        </div>
      </template>
    </slider-container>
    <!-- ////// -->
    <!-- banner -->
    <!-- ////// -->
    <sale-baner />
    <!-- ///////// -->
    <!-- Top Deals -->
    <!-- ///////// -->
    <slider-container
      :title="topProducts?.text"
      :cardCount="topProducts.content.length"
      :cardSize="305"
    >
      <template #product>
        <div
          class="cards slide-items w-[295px] h-[452px] ml-[10px]"
          v-for="(product, index) in topProducts?.content"
          :key="index"
        >
          <product-card
            :product="product"
            :productType="topProducts.type"
            @addToFavorts="handelChangesProduct"
            @removeFromFavorits="handelChangesProduct"
            @incrementCountToCart="handelChangesProduct"
            @decrementCountFromCart="handelChangesProduct"
          />
        </div>
      </template>
    </slider-container>
    <!-- ///////// -->
    <!-- gift card -->
    <!-- ///////// -->
    <gift-cards />
    <!-- ///////// -->
    <!-- popular products -->
    <!-- ///////// -->
    <slider-container
      :title="popularProducts?.text"
      :cardCount="popularProducts.content.length"
      :cardSize="305"
    >
      <template #product>
        <div
          class="cards slide-items w-[295px] h-[452px] ml-[10px]"
          v-for="(product, index) in popularProducts?.content"
          :key="index"
        >
          <product-card
            :product="product"
            :productType="popularProducts.type"
            @addToFavorts="handelChangesProduct"
            @removeFromFavorits="handelChangesProduct"
            @incrementCountToCart="handelChangesProduct"
            @decrementCountFromCart="handelChangesProduct"
          />
        </div>
      </template>
    </slider-container>
    <!-- ///////////////// -->
    <!-- countdown section -->
    <!-- ///////////////// -->
    <countdown-banner />
    <!-- ///////// -->
    <!-- news Products -->
    <!-- ///////// -->
    <slider-container
      :title="newsProducts?.text"
      :cardCount="newsProducts.content.length"
      :cardSize="305"
    >
      <template #product>
        <div
          class="cards slide-items w-[295px] h-[452px] ml-[10px]"
          v-for="(product, index) in newsProducts?.content"
          :key="index"
        >
          <product-card
            :product="product"
            :productType="newsProducts.type"
            @addToFavorts="handelChangesProduct"
            @removeFromFavorits="handelChangesProduct"
            @incrementCountToCart="handelChangesProduct"
            @decrementCountFromCart="handelChangesProduct"
          />
        </div>
      </template>
    </slider-container>
    <mobile-footer class="sm:hidden block" />
    <main-footer />
  </div>
</template>

<script setup>
import MainNav from "~/components/main-nav.vue";
import topNav from "~/components/top-nav.vue";
import CategorysBar from "../components/categorysBar.vue";
import Baner from "~/components/baner.vue";
import BannerTowSections from "~/components/bannerTowSections.vue";
import sliderContainer from "~/components/slider-container.vue";
import categoryCards from "~/components/category-cards.vue";
import SaleBaner from "~/components/sale-baner.vue";
import ProductCard from "~/components/product-card.vue";
import giftCards from "~/components/gift-cards.vue";
import CountdownBanner from "~/components/countdown-banner.vue";
import mainFooter from "~/components/main-footer.vue";
import Drawer from "~/components/drawer.vue";
import MobileFooter from "~/components/mobile-footer.vue";
const lat = ref(null);
const lng = ref(null);
const isOpenDrawer = ref(false);
const {
  data: categorys_data,
  error,
  pending,
  refresh,
} = await useFetch(
  `https://phpv8.aait-d.com/dukanv2/public/api/website/categories`,
  {
    headers: { "Accept-Language": "ar" },
  }
);
const { data: homeApi } = await useFetch(
  `https://phpv8.aait-d.com/dukanv2/public/api/website/home?lat=${lat.value}&lng=${lng.value}`,
  {
    headers: { "Accept-Language": "en" },
  }
);
// filter main data to find top-deal object
const topProducts = computed(() => {
  const mainObj = homeApi.value;
  const { data } = mainObj;
  console.log(data);
  const filtration = data.find((el) => {
    return el.type === "top_deal_products";
  });
  return filtration;
});
// toggle drawer
const toggleDrawer = () => {
  isOpenDrawer.value = !isOpenDrawer.value;
  console.log(isOpenDrawer.value);
};
// filter main data to find most_popular_products object
const popularProducts = computed(() => {
  const mainObj = homeApi.value;
  const { data } = mainObj;
  console.log(data);
  const filtration = data.find((el) => {
    return el.type === "most_popular_products";
  });
  return filtration;
});
// filter main data to find news_products object
const newsProducts = computed(() => {
  const mainObj = homeApi.value;
  const { data } = mainObj;
  console.log(data);
  const filtration = data.find((el) => {
    return el.type === "news_products";
  });
  return filtration;
});
const getCurentLocation = () => {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition((position) => {
      lat.value = position.coords.latitude;
      lng.value = position.coords.longitude;
    });
  } else {
    console.log("Geolocation is not supported by this browser.");
  }
};
// handler function to handel all changes for all product
const handelChangesProduct = ({
  productId,
  propAction /*prop i will do action for change it*/,
  addOrRemove /*Boolean*/,
  type /*object type*/,
}) => {
  const { data } = homeApi.value;
  // get index of object by type
  const getType = data.findIndex((el) => el.type == type);
  // get index product by id
  const indx = data[getType]["content"].findIndex((el) => el.id == productId);
  // do action
  switch (propAction) {
    case "is_fav":
      data[getType]["content"][indx]["is_fav"] = addOrRemove;
      console.log(data[getType]["content"][indx]["is_fav"]);
      break;
    case "product_id_in_cart":
      if (addOrRemove) {
        data[getType]["content"][indx]["product_id_in_cart"] = addOrRemove;
        Number(data[getType]["content"][indx]["in_cart_count"]++);
      } else {
        Number(data[getType]["content"][indx]["in_cart_count"]--);
      }
      break;
    default:
  }
};
onBeforeMount(() => {
  getCurentLocation();
});
</script>

<style lang="scss">
.slide-items {
  display: inline-block;
  margin-left: 30px;
  white-space: normal;
  text-overflow: ellipsis;
  scroll-snap-align: start;
}
.cards {
}
</style>