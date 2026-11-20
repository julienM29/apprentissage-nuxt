<script setup lang="ts">
const year = new Date().getFullYear()
</script>

<template>
  <UFooter>
    <template #left>
      <p class="text-sm text-muted">
        © {{ year }} Ma Biblio
      </p>
    </template>

    <template #right>
      <UButton
        icon="i-simple-icons-github"
        color="neutral"
        variant="ghost"
        to="https://github.com/JulienM29/apprentissage-nuxt"
        target="_blank"
        aria-label="Code source sur GitHub (nouvel onglet)"
      />
    </template>
  </UFooter>
</template>