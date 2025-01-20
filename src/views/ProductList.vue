<script setup lang="ts">
import TheProduct from "@/components/TheProduct.vue";
import type { Product } from "@/models/product.type";

defineProps<{
  products: Product[];
}>();
</script>
<template>
  <div>
    <h1>Liste des produits</h1>
    <div class="product-list">
      <TheProduct
        v-for="product in products"
        :key="product.id"
        :product="product"
      />
    </div>
  </div>
</template>

<style scoped>
.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}
</style>
