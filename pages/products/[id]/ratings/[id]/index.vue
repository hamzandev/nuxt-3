<script setup lang="ts">
import { useRoute } from "nuxt/app";

const { params } = useRoute();

function showParams(){
    console.log(params);
}
</script>

<template>
  <div>
    <UButton @click="showParams">Show Params</UButton>
  </div>
</template>