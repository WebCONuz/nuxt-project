<script setup>
definePageMeta({
  layout: "products",
});

const products = ref(null);
onMounted(async () => {
  try {
    fetch("https://fakestoreapi.com/products")
      .then((res) => res.json())
      .then((json) => {
        products.value = json;
      });
  } catch (e) {
    console.log(e);
  }
});
</script>

<template>
  <div class="container mx-auto p-4">
    <h1 class="text-3xl text-center my-6 font-semibold">
      Hello This is Product Page.
    </h1>
    <div class="grid grid-cols-4 gap-5">
      <template v-for="item in products" :key="item?.id">
        <ProductCard :product="item" />
      </template>
    </div>
  </div>
</template>

<style scoped></style>
