<script lang="ts" setup>
const menus = [
  {
    id: 1,
    title: "Home",
    href: "/",
  },
  {
    id: 2,
    title: "Products",
    href: "/products",
  },
  {
    id: 3,
    title: "Setting",
    href: "/setting",
  },
];
</script>

<template>
  <nav class="py-3 shadow-sm">
    <div class="container mx-auto flex items-center justify-between gap-x-10">
      <div class="flex justify-between">
        <span class="text-lg font-bold font-mono">Logo</span>
      </div>
      <div class="flex items-center gap-x-8">
        <NuxtLink
          active-class="text-primary"
          inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200"
          v-for="menu in menus"
          :to="menu.href"
          :key="menu.id"
        >
          {{ menu.title }}
        </NuxtLink>
      </div>
      <div class="flex gap-x-3 flex-row-reverse items-center">
        <!-- <UButton size="sm" variant="solid" label="Sign In" to="/" /> -->
        <command-pallete />
      </div>
    </div>
  </nav>
</template>