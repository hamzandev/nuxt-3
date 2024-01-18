
<template>
  <div class="grid gap-5 md:grid-cols-4 grid-cols-2">
    <div v-if="pending">
      <p>Loading...</p>
    </div>
    <NuxtLink
      v-else
      class="p-4 bg-gray-900 rounded-lg shadow-md"
      v-for="product in products"
      :to="'/products/' + product.id"
      :product="product"
      :key="product.id"
    >
      <h2>{{ product.title }}</h2>
    </NuxtLink>
  </div>
</template>

<script setup>
const { data: products, pending } = useFetch(
  "https://fakestoreapi.com/products"
);
</script>