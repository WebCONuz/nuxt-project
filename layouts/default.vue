<script setup></script>

<template>
  <div>
    <header class="bg-gray-50 shadow-lg sticky top-0 left-0 w-full">
      <nav
        class="container flex items-center justify-between h-[70px] px-4 mx-auto"
      >
        <nuxt-link to="/" class="font-bold">Miniature</nuxt-link>
        <ul class="flex gap-4">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li class="button">
            <NuxtLink to="/products" class="btn">Product</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>

    <!-- output the page content -->
    <div class="container mx-auto p-4">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: #12b488;
}
.button .router-link-exact-active {
  color: white;
}
</style>
