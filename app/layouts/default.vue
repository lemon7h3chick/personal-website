<script setup lang="ts">
import { profile } from '~/data/profile'
</script>

<template>
  <div class="layout-shell flex min-h-screen flex-col">
    <SiteHeader />
    <main id="main-content" class="flex-1">
      <slot />
    </main>
    <footer class="site-footer page-container mx-auto flex w-full items-center justify-between">
      <span>© {{ new Date().getFullYear() }} {{ profile.name }}</span>
      <NuxtLink to="/profile" class="footer-link">
        A little more about me
        <UiIcon name="arrow-up-right" :size="14" :stroke-width="1.8" />
      </NuxtLink>
    </footer>
  </div>
</template>
