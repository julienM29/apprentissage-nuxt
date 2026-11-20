<script setup lang="ts">
import AppFooter from "~/components/AppFooter.vue";
</script>
<template>
  <div>
    <a
        href="#contenu"
        class="sr-only focus:not-sr-only focus:fixed focus:top-4 focus:left-4 focus:z-100
             focus:rounded-md focus:bg-default focus:px-4 focus:py-2
             focus:ring-2 focus:ring-primary"
    >
      Aller au contenu
    </a>

    <AppHeader />

    <UMain id="contenu" tabindex="-1" class="focus:outline-none">
      <slot />
    </UMain>

    <AppFooter />
  </div>
</template>