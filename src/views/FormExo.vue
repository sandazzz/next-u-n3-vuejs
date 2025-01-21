<script setup lang="ts">
import { reactive, ref } from "vue";
import type { FormulaireInscription } from "@/models/form.type";
import FicheRecap from "@/components/FicheRecap.vue";

const form = reactive<FormulaireInscription>({
  nom: "",
  prenom: "",
  email: "",
  sexe: "",
  institut: "",
  adresse: "",
  codePostal: "",
  ville: "",
});

const isSubmitted = ref(false);

// Fonction pour valider le formulaire
const validateForm = (): boolean => {
  return Object.values(form).every((value) => value.trim() !== "");
};

// Fonction pour soumettre le formulaire
const handleSubmit = () => {
  if (validateForm()) {
    isSubmitted.value = true;
    alert("Formulaire soumis avec succès !");
    console.log("Formulaire soumis :", form);
  } else {
    alert("Veuillez remplir tous les champs avant de valider.");
  }
};

const handleCancel = () => {
  form.nom = "";
  form.prenom = "";
  form.email = "";
  form.sexe = "";
  form.institut = "";
  form.adresse = "";
  form.codePostal = "";
  form.ville = "";

  isSubmitted.value = false;
  alert("Formulaire réinitialisé.");
};
</script>

<template>
  <div
    class="min-h-screen bg-gray-100 flex items-center justify-center flex-col"
  >
    <FicheRecap v-bind="form" v-if="isSubmitted" />

    <div class="bg-white shadow-lg rounded-lg p-6 w-full max-w-lg" v-else>
      <h1 class="text-2xl font-bold text-gray-800 mb-6 text-center">
        Formulaire d'inscription
      </h1>
      <form @submit.prevent="handleSubmit" class="space-y-4">
        <!-- Nom -->
        <div>
          <label for="nom" class="block text-gray-700 font-medium mb-1"
            >Nom</label
          >
          <input
            v-model="form.nom"
            type="text"
            id="nom"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Prénom -->
        <div>
          <label for="prenom" class="block text-gray-700 font-medium mb-1"
            >Prénom</label
          >
          <input
            v-model="form.prenom"
            type="text"
            id="prenom"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Email -->
        <div>
          <label for="email" class="block text-gray-700 font-medium mb-1"
            >Email</label
          >
          <input
            v-model="form.email"
            type="email"
            id="email"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Sexe -->
        <div>
          <span class="block text-gray-700 font-medium mb-1">Sexe</span>
          <div class="flex items-center space-x-4">
            <label class="flex items-center">
              <input
                v-model="form.sexe"
                type="radio"
                value="Homme"
                class="mr-2"
              />
              Homme
            </label>
            <label class="flex items-center">
              <input
                v-model="form.sexe"
                type="radio"
                value="Femme"
                class="mr-2"
              />
              Femme
            </label>
          </div>
        </div>

        <!-- Nom de l'institut -->
        <div>
          <label for="institut" class="block text-gray-700 font-medium mb-1"
            >Nom de l'institut</label
          >
          <input
            v-model="form.institut"
            type="text"
            id="institut"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Adresse -->
        <div>
          <label for="adresse" class="block text-gray-700 font-medium mb-1"
            >Adresse</label
          >
          <input
            v-model="form.adresse"
            type="text"
            id="adresse"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Code postal -->
        <div>
          <label for="codePostal" class="block text-gray-700 font-medium mb-1"
            >Code postal</label
          >
          <input
            v-model="form.codePostal"
            type="text"
            id="codePostal"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Ville -->
        <div>
          <label for="ville" class="block text-gray-700 font-medium mb-1"
            >Ville</label
          >
          <input
            v-model="form.ville"
            type="text"
            id="ville"
            class="w-full border border-gray-300 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Boutons -->
        <div class="flex justify-evenly">
          <button
            type="submit"
            class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 transition"
          >
            Valider
          </button>
          <button
            type="button"
            @click="handleCancel"
            class="bg-gray-500 text-white px-4 py-2 rounded-lg hover:bg-gray-600 transition"
          >
            Annuler
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
