<script setup lang="ts">
const toast = useToast();
const page = ref(1);
const items = ref(Array(55));
</script>

<template>
  <div>
    <div class="grid md:grid-cols-4 gap-5 my-7 md:me-3">
      <div v-for="i in 6" :key="i">
        <div class="flex items-center gap-2">
          <USkeleton class="h-10 w-12"/>
          <div class="space-y-2 w-full">
            <USkeleton class="h-4 w-full" />
            <USkeleton class="h-4 w-[80%]" />
          </div>
        </div>
      </div>
    </div>
    <div class="overflow-x-auto sm:w-auto w-screen">
      <Table />
    </div>
  </div>
</template>