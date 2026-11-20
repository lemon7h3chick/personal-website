<script setup lang="ts">
import { profile } from '~/data/profile'

useSeoMeta({
  title: `Profile — ${profile.name}`,
  description: profile.introduction,
  ogTitle: `Profile — ${profile.name}`,
  ogDescription: profile.introduction,
  themeColor: '#101310',
})
</script>

<template>
  <div class="page-container page-content profile-page mx-auto w-full">
    <section class="profile-heading animate-in" aria-labelledby="profile-title">
      <div>
        <p class="eyebrow"><span class="eyebrow-dot" /> Profile <span class="eyebrow-divider">/</span> A little context</p>
        <h1 id="profile-title" class="profile-title">Curious by nature.<br><em>Learning by building.</em></h1>
      </div>
      <p class="profile-intro">{{ profile.introduction }}</p>
    </section>

    <section class="profile-overview" aria-label="Personal and education information">
      <article class="about-card panel animate-in animate-delay-1">
        <div class="card-heading">
          <span class="section-index">01 / A bit about me</span>
          <span class="about-initials" aria-hidden="true">{{ profile.initials }}</span>
        </div>
        <h2>{{ profile.name }}</h2>
        <p>{{ profile.shortIntroduction }}</p>
        <div class="about-tags"><span>Thoughtful design</span><span>Curious mind</span></div>
      </article>

      <article class="education-card panel animate-in animate-delay-2">
        <div class="card-heading">
          <span class="section-index">02 / Education</span>
          <span class="education-icon"><UiIcon name="graduation" :size="19" :stroke-width="1.7" /></span>
        </div>
        <div class="education-status"><span class="status-dot" />{{ profile.education.status }}</div>
        <h2>{{ profile.education.program }}</h2>
        <p>{{ profile.education.description }}</p>
        <div class="education-footer"><span>{{ profile.education.level }}</span><span>Information technology</span></div>
      </article>
    </section>

    <section class="content-section" aria-labelledby="skills-title">
      <div class="section-header animate-in">
        <div>
          <p class="section-index">03 / Tools in progress</p>
          <h2 id="skills-title">Building my <em>foundation.</em></h2>
        </div>
        <p>Still learning, always curious.<br>These are the things I’m exploring.</p>
      </div>
      <div class="skills-grid">
        <article v-for="(skill, index) in profile.skills" :key="skill.name" class="skill-card panel animate-in" :style="{ '--card-order': index }">
          <div class="skill-card-top"><span class="skill-icon"><UiIcon :name="skill.icon" :size="19" /></span><span class="skill-number">0{{ index + 1 }}</span></div>
          <h3>{{ skill.name }}</h3>
          <p>{{ skill.description }}</p>
          <span class="skill-progress"><span /></span>
          <span class="skill-label">In progress</span>
        </article>
      </div>
    </section>

    <section class="profile-lower-grid" aria-label="Interests and hobbies">
      <article class="list-card panel animate-in">
        <div class="card-heading"><span class="section-index">04 / What catches my eye</span><UiIcon name="arrow-down-right" :size="18" class="list-heading-icon" /></div>
        <h2>Things I’m <em>into.</em></h2>
        <ul class="icon-list">
          <li v-for="interest in profile.interests" :key="interest.name">
            <span class="list-icon"><UiIcon :name="interest.icon" :size="18" /></span>
            <span>{{ interest.name }}</span>
            <UiIcon name="arrow-up-right" class="list-arrow" :size="15" />
          </li>
        </ul>
      </article>

      <article class="list-card panel animate-in animate-delay-1">
        <div class="card-heading"><span class="section-index">05 / Outside the browser</span><span class="hobby-stamp">LIFE / 02</span></div>
        <h2>Off-screen <em>moments.</em></h2>
        <ul class="icon-list">
          <li v-for="hobby in profile.hobbies" :key="hobby.name">
            <span class="list-icon"><UiIcon :name="hobby.icon" :size="18" /></span>
            <span>{{ hobby.name }}</span>
            <UiIcon name="arrow-up-right" class="list-arrow" :size="15" />
          </li>
        </ul>
      </article>
    </section>

    <NuxtLink class="profile-end-card animate-in" to="/">
      <span class="section-index">Thanks for getting to know me</span>
      <span class="end-card-copy">Let’s keep<br><em>exploring.</em></span>
      <span class="end-card-arrow"><UiIcon name="arrow-up-right" :size="21" /></span>
    </NuxtLink>
  </div>
</template>
