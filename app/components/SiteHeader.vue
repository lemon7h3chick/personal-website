<script setup lang="ts">
import { profile } from '~/data/profile'

const route = useRoute()
const navigation = [
  { label: 'Home', to: '/' },
  { label: 'Profile', to: '/profile' },
]
</script>

<template>
  <header class="site-header page-container mx-auto flex w-full items-center justify-between">
    <NuxtLink class="brand-link" to="/" :aria-label="`${profile.name} — home`">
      <span class="brand-mark" aria-hidden="true">keki</span>
      <span class="brand-copy">
        <span class="brand-name">{{ profile.name }}</span>
        <span class="brand-role">Personal portfolio</span>
      </span>
    </NuxtLink>

    <nav class="main-nav" aria-label="Main navigation">
      <NuxtLink
        v-for="item in navigation"
        :key="item.to"
        :to="item.to"
        :aria-current="route.path === item.to ? 'page' : undefined"
        class="nav-link"
      >
        {{ item.label }}
      </NuxtLink>
      <NuxtLink class="nav-cta" to="/profile">
        About me
        <UiIcon name="arrow-up-right" :size="15" :stroke-width="1.8" />
      </NuxtLink>
    </nav>
  </header>
</template>
