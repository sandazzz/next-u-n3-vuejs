<script setup lang="ts">
import TheProduct from "@/components/TheProduct.vue";
import type { Product } from "@/models/product.type";

defineProps<{
  products: Product[];
}>();
</script>

<template>
  <div class="w-full min-h-screen flex flex-col justify-center">
    <h1 class="text-2xl font-bold text-center mb-6">Liste des produits</h1>
    <div class="flex gap-4 justify-center items-center">
      <TheProduct
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>
