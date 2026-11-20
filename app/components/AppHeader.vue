<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const route = useRoute()

const items = computed<NavigationMenuItem[]>(() => [
  { label: 'Accueil', to: '/' },
  {
    label: 'Livres',
    to: '/livres',
    active: route.path.startsWith('/livres'),
  },
  // TODO : ajoute le lien "À propos"
])
</script>

<template>
  <UHeader title="Ma Biblio" to="/">
    <UNavigationMenu :items="items" />
    <template #right>
      <UColorModeButton />
    </template>
  </UHeader>
</template>