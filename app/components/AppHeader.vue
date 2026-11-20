<script setup lang="ts">
import type {NavigationMenuItem} from '@nuxt/ui'

const route = useRoute()

const items = computed<NavigationMenuItem[]>(() => [
  {label: 'Accueil', to: '/'},
  {
    label: 'Livres',
    to: '/livres',
    active: route.path.startsWith('/livres'),
  },
  {
    label: 'A propos',
    to: '/a-propos',
    active: route.path.startsWith('/a-propos'),
  },
])
</script>

<template>
  <UHeader title="Ma Biblio" to="/">
    <!-- Grand écran : la nav au centre -->
    <UNavigationMenu :items="items"/>

    <!-- À droite : le bouton thème -->
    <template #right>
      <UColorModeButton/>
    </template>

    <!-- Petit écran : le contenu du menu burger -->
    <template #body>
      <UNavigationMenu :items="items" orientation="vertical"/>
    </template>
  </UHeader>
</template>