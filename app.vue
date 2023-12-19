<template>
  <div class="bg-[#F9F9F9]">
    <NuxtPage />
  </div>
</template>
<script setup>
import { ofetch } from "ofetch";

globalThis.$fetch = ofetch.create({
  baseUrl: "https://phpv8.aait-d.com/dukanv2/public/api/website/categories",
  onRequest: () => {},
});
</script>
