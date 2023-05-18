<script setup>
definePageMeta({
  layout: "products",
});

// fetch the products
const { data: products } = await useFetch("https://fakestoreapi.com/products");
</script>

<template>
  <div class="container mx-auto p-4">
    <h1 class="text-3xl text-center my-6 font-semibold">
      Hello This is Product Page.
    </h1>
    <div class="grid grid-cols-4 gap-5">
      <diV v-for="p in products">
        <ProductCard :product="p" />
      </diV>
    </div>
  </div>
</template>

<style scoped></style>
