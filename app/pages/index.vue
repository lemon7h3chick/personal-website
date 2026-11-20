<script setup lang="ts">
import { profile } from '~/data/profile'

useSeoMeta({
  title: `${profile.name} — Personal Portfolio`,
  description: profile.shortIntroduction,
  ogTitle: `${profile.name} — Personal Portfolio`,
  ogDescription: profile.shortIntroduction,
  themeColor: '#101310',
})
</script>

<template>
  <div class="page-container page-content mx-auto w-full">
    <section class="home-hero" aria-labelledby="home-title">
      <div class="hero-copy animate-in">
        <p class="eyebrow"><span class="eyebrow-dot" /> Independent learner <span class="eyebrow-divider">/</span> Web development</p>
        <h1 id="home-title" class="hero-title">
          Hello, I’m<br>
          <span class="hero-name">John Keneth <em>Diola.</em></span>
        </h1>
        <p class="hero-description">{{ profile.shortIntroduction }}</p>
        <div class="hero-actions">
          <NuxtLink class="button button-primary" to="/profile">
            Get to know me
            <UiIcon name="arrow-right" :size="17" :stroke-width="1.8" />
          </NuxtLink>
          <span class="hero-note"><UiIcon name="arrow-down-right" :size="16" /> A small corner of the web, by me</span>
        </div>
      </div>

      <div class="hero-portrait animate-in animate-delay-1">
        <div class="portrait-topline"><span>JKD / 01</span><span>STUDY / 01</span></div>
        <div class="portrait-art">
          <div class="portrait-orbit orbit-one" aria-hidden="true" />
          <div class="portrait-orbit orbit-two" aria-hidden="true" />
          <div class="portrait-orbit orbit-three" aria-hidden="true" />
          <img class="portrait-photo" src="/profile.jpg" :alt="profile.name" width="960" height="960">
          <span class="portrait-star star-one" aria-hidden="true" />
          <span class="portrait-star star-two" aria-hidden="true" />
          <span class="portrait-coordinate" aria-hidden="true">IDEAS →<br>PRACTICE</span>
        </div>
        <div class="portrait-caption">
          <span class="caption-label">Currently</span>
          <span class="caption-value">{{ profile.role }}</span>
          <span class="caption-indicator" aria-hidden="true" />
        </div>
      </div>
    </section>

    <section class="home-grid" aria-label="A little about me">
      <article class="welcome-card panel animate-in animate-delay-2">
        <div class="card-heading">
          <span class="section-index">01 / A warm welcome</span>
          <UiIcon class="card-sparkle" name="sparkles" :size="18" :stroke-width="1.7" />
        </div>
        <h2>Glad you’re<br><em>here.</em></h2>
        <p>{{ profile.introduction }}</p>
        <NuxtLink class="text-link" to="/profile">
          A little more about me
          <UiIcon name="arrow-right" :size="16" :stroke-width="1.8" />
        </NuxtLink>
      </article>

      <article class="focus-card panel animate-in animate-delay-3">
        <span class="section-index">02 / What I’m learning</span>
        <div class="focus-graphic" aria-hidden="true">
          <span class="focus-orb" />
          <span class="focus-cross">+</span>
          <span class="focus-code">&lt; web /&gt;</span>
          <span class="focus-caption">curiosity → practice</span>
        </div>
        <div class="focus-copy">
          <h2>From idea<br>to <em>interface.</em></h2>
          <p>Exploring the building blocks of the web, one new thing at a time.</p>
        </div>
      </article>

      <NuxtLink class="profile-callout panel animate-in animate-delay-3" to="/profile">
        <span class="section-index">03 / Take a look around</span>
        <span class="callout-copy">Curious about<br>the person <em>behind</em><br>the pixels?</span>
        <span class="callout-bottom"><span>Explore my profile</span><span class="callout-arrow"><UiIcon name="arrow-right" :size="19" /></span></span>
      </NuxtLink>
    </section>

    <div class="page-endnote"><span /> Thanks for stopping by <span /></div>
  </div>
</template>
