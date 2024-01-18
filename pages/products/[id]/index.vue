<script setup lang="ts">
const { params } = useRoute();
const { data: product, pending, error } = useFetch<any>(
  "https://fakestoreapi.com/products/" + params?.id
);
</script>

<template>
  <p v-if="pending">Loading...</p>
  <div class="md:w-[80%] p-5 card border border-gray-800 rounded-lg" v-else>
    <div class="flex justify-between mb-5">
      <h1 class="text-xl mb-5 font-bold">Product Detail</h1>
      <Slider :product="product"/>
    </div>
    <h3 class="text-3xl mb-3 font-extrabold">{{ product.title }}</h3>
    <div class="flex gap-3 items-center mt-3">
      <UBadge variant="soft" color="yellow">{{ product.category }}</UBadge>
      <UIcon name="i-heroicons-star-solid" class="bg-orange-300 scale-150"/>
      <ULabel>{{ product.rating.rate }} ({{ product.rating.count }})</ULabel>
    </div>
    <div class="image aspect-video md:h-[80vh] h-[30vh] py-5">
      <img :src="product.image" :alt="product.id" class="object-cover rounded-lg object-top w-full h-full">
    </div>
    <p class="">{{ product.description }}</p>
  </div>
</template>
