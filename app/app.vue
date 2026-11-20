<template>
  <div class="site-frame flex min-h-screen flex-col">
    <NuxtRouteAnnouncer />
    <a class="skip-link" href="#main-content">Skip to content</a>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
