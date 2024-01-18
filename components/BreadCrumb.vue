<script setup>
const links = [{
  label: 'Home',
  icon: 'i-heroicons-home',
  to: '/'
}, {
  label: 'Products',
  icon: 'i-heroicons-square-3-stack-3d'
}, {
  label: 'Setting',
  icon: 'i-heroicons-link'
}]
</script>

<template>
  <UBreadcrumb :links="links" />
</template>

