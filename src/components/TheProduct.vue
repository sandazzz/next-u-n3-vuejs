<script setup lang="ts">
import type { Product } from '@/models/product.type';

defineProps<{
  product: Product;
}>();
</script>

<template>
  <article>
    <h2 class="product-label">{{ product.label }}</h2>
    <p class="product-description">{{ product.description }}</p>
    <p class="product-status">
      <span
        :class="{ available: product.qte > 0, unavailable: product.qte === 0 }"
      >
        {{ product.qte > 0 ? "Disponible" : "Indisponible" }}
      </span>
    </p>
  </article>
</template>

<style scoped>
.product-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 16px;
  width: 300px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  margin: 10px;
  text-align: center;
  background-color: #f9f9f9;
  transition: transform 0.3s, box-shadow 0.3s;
}

.product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

.product-label {
  font-size: 1.5em;
  color: #333;
  margin-bottom: 8px;
}

.product-description {
  font-size: 1em;
  color: #555;
  margin-bottom: 12px;
}

.product-status {
  font-weight: bold;
  font-size: 1.2em;
}

.product-status .available {
  color: green;
}

.product-status .unavailable {
  color: red;
}
</style>
