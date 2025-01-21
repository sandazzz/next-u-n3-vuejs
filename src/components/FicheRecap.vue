<script setup lang="ts">
import type { FormulaireInscription } from "@/models/form.type";

defineProps<FormulaireInscription>();
</script>

<template>
  <div
    class="max-w-md mx-auto p-6 bg-white rounded-lg shadow-lg ring-1 ring-gray-200"
  >
    <h1 class="text-2xl font-bold text-gray-800 mb-4 border-b pb-2">
      Détails de l'inscription
    </h1>
    <dl class="divide-y divide-gray-200">
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Nom</dt>
        <dd class="text-sm text-gray-800">{{ nom }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Prénom</dt>
        <dd class="text-sm text-gray-800">{{ prenom }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Email</dt>
        <dd class="text-sm text-gray-800">{{ email }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Sexe</dt>
        <dd class="text-sm text-gray-800">{{ sexe }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Institut</dt>
        <dd class="text-sm text-gray-800">{{ institut }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Adresse</dt>
        <dd class="text-sm text-gray-800">{{ adresse }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Code postal</dt>
        <dd class="text-sm text-gray-800">{{ codePostal }}</dd>
      </div>
      <div class="py-3 grid grid-cols-2 gap-4">
        <dt class="text-sm font-semibold text-gray-600">Ville</dt>
        <dd class="text-sm text-gray-800">{{ ville }}</dd>
      </div>
    </dl>
  </div>
</template>
