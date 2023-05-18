<script setup>
const { id } = useRoute().params;

const url = "https://fakestoreapi.com/products/" + id;
const { data: product } = await useFetch(url, { key: id });

definePageMeta({
  layout: "products",
});
</script>

<template>
  <div>
    <ProductDetails :product="product" />
  </div>
</template>

<style scoped></style>
