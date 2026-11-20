<script setup lang="ts">
useHead({
  titleTemplate: title => title ? `${title} · Ma Biblio` : 'Ma Biblio',
})
</script>

<template>
  <UApp> <!-- bOITE DE NUXT UI qui englobe tout -->
    <NuxtRouteAnnouncer />
    <NuxtLayout> <!-- Charge chaque layout - base : default.vue -->
      <NuxtPage /> <!-- page -->
    </NuxtLayout>
  </UApp>
</template>
