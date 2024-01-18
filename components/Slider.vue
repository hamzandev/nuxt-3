<script setup lang="ts">
import type { FormError, FormSubmitEvent } from "#ui/types";

const props = defineProps({
  product: {
    type: Object,
    required: true,
  },
});

const { product } = props;

const isOpen = ref(false);
const state = reactive({
  title: product?.title,
  description: product?.description,
});

const validate = (state: any): FormError[] => {
  const errors = [];
  if (!state.email) errors.push({ path: "email", message: "Required" });
  if (!state.password) errors.push({ path: "password", message: "Required" });
  return errors;
};

async function onSubmit(event: FormSubmitEvent<any>) {}
const toast = useToast()
</script>

<template>
  <div>
    <UButton
      icon="i-heroicons-pencil-square-solid"
      label="Edit"
      @click="isOpen = true"
    />

    <USlideover v-model="isOpen">
      <div class="p-6 flex-1">
        <div class="mb-5">
          <h1 class="text-2xl font-bold">Edit Product Detail</h1>
        </div>
        <UForm
          :validate="validate"
          :state="state"
          class="space-y-4"
          @submit="onSubmit"
        >
          <UFormGroup label="Product Title" name="title">
            <UTextarea v-model="state.title" />
          </UFormGroup>

          <UFormGroup label="Description" name="description">
            <UTextarea
              rows="8"
              v-model="state.description"
              type="description"
            />
          </UFormGroup>

          <div class="flex justify-end">
            <UButton @click="()=>{isOpen = false; toast.add({title: 'Your changes was saved!'})}" type="submit" icon="i-heroicons-check">
              Save Change
            </UButton>
          </div>
        </UForm>
      </div>
    </USlideover>
  </div>
</template>

