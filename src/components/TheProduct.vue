<script setup lang="ts">
import type { Product } from "@/models/product.type";

defineProps<{
  product: Product;
}>();
</script>

<template>
  <div
    class="border border-gray-300 rounded-lg shadow-md p-4 bg-white w-64 transition-transform hover:scale-105 hover:shadow-lg"
  >
    <h2 class="text-lg font-semibold text-gray-800 mb-2">
      {{ product.label }}
    </h2>
    <p class="text-gray-600 mb-4">{{ product.description }}</p>
    <p class="font-bold text-center">
      <span v-if="product.qte > 0" class="text-green-500">Disponible</span>
      <span v-else class="text-red-500">Indisponible</span>
    </p>
  </div>
</template>
