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
    <h1 class="text-center text-2xl font-bold my-6">{{ product.title }}</h1>
    <p class="text-center text-lg text-green-500 mb-6">
      Product ID is equal {{ product.id }}
    </p>
  </div>
</template>

<style scoped></style>
