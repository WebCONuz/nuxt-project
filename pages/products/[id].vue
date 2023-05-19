<script setup>
const { id } = useRoute().params;
const url = "https://fakestoreapi.com/products/" + id;
const { pending, data: product } = await useLazyAsyncData("product", () =>
  $fetch(url)
);

watch(product, (newCount) => (product.value = newCount));

if (!product.value) {
  throw createError({
    statusCode: 404,
    statusMessage: "Product is not found",
    fatal: true,
  });
}

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
