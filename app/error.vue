<script setup lang="ts">
import type { NuxtError } from '#app'

// Nuxt passe automatiquement l'erreur en prop
const props = defineProps<{ error: NuxtError }>()

// Est-ce une page introuvable (404) ?
const isNotFound = computed(() => props.error.statusCode === 404)

// Titre de l'onglet (error.vue remplace app.vue : pas de titleTemplate ici)
useSeoMeta({
  title: () => isNotFound.value ? 'Page introuvable · Ma Biblio' : 'Erreur · Ma Biblio',
})

// Efface l'erreur puis redirige vers l'accueil
function goHome() {
  clearError({ redirect: '/' })
}
</script>

<template>
  <UApp>
    <NuxtLayout>
      <UContainer class="py-16 text-center">
        <p class="text-6xl font-bold text-primary">
          {{ error.statusCode }}
        </p>

        <h1 class="mt-4 text-2xl font-semibold text-highlighted">
          {{ isNotFound ? 'Page introuvable' : 'Une erreur est survenue' }}
        </h1>

        <p class="mt-2 text-muted">
          {{ isNotFound
          ? 'La page que vous cherchez n’existe pas ou a été déplacée.'
          : 'Veuillez réessayer dans quelques instants.' }}
        </p>

        <UButton
            class="mt-8"
            label="Retour à l’accueil"
            @click="goHome"
        />
      </UContainer>
    </NuxtLayout>
  </UApp>
</template>