<script setup>
import heroImage from '../1b.png'
import retroImage from '../RetroASCII.webp'
import vinylImage from '../22.webp'
import classicImage from '../classic.webp'
import neoImage from '../neo.webp'
import demoVideo from '../demo.mp4'

const latestReleaseUrl = 'https://github.com/leeseomin/VoidPlayer-releases/releases/latest'
const releasesUrl = 'https://github.com/leeseomin/VoidPlayer-releases/releases'
const youtubeUrl = 'https://www.youtube.com/watch?v=vE5VrxtTB-Y'

const featureHighlights = [
  {
    eyebrow: 'Local-first',
    title: 'Play the files already on your Mac',
    copy: 'Void Player supports common local audio formats including MP3, M4A, WAV, and FLAC.',
  },
  {
    eyebrow: 'Verified release',
    title: 'Apple-notarized DMG',
    copy: 'Download from GitHub Releases and install a signed distribution artifact built for macOS.',
  },
  {
    eyebrow: 'Lightweight',
    title: 'Swift app, tiny footprint',
    copy: 'A focused native player with a release size around 3.8MB and no account workflow in the way.',
  },
  {
    eyebrow: 'Library flow',
    title: 'Topic tabs and dual shuffle',
    copy: 'Organize tracks by category, reorder lists, or shuffle playback while keeping the queue intact.',
  },
]

const modes = [
  {
    name: 'RetroASCII',
    image: retroImage,
    copy: 'Terminal-inspired controls with a sharper visual rhythm.',
  },
  {
    name: 'Vinyl',
    image: vinylImage,
    copy: 'A record-deck presentation for browsing and playback.',
  },
  {
    name: 'Classic',
    image: classicImage,
    copy: 'A quiet, familiar player layout for everyday listening.',
  },
  {
    name: 'Neo',
    image: neoImage,
    copy: 'A compact modern surface with clear transport controls.',
  },
]
</script>

<template>
  <main class="page-shell">
    <a class="github-corner" href="https://github.com/leeseomin/VoidPlayer-releases" target="_blank" rel="noopener">
      <svg viewBox="0 0 16 16" width="24" height="24" fill="currentColor" aria-label="GitHub">
        <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
      </svg>
    </a>
    <section class="hero-section" aria-labelledby="hero-title">
      <div class="hero-copy">
        <p class="release-label">macOS release page</p>
        <h1 id="hero-title">Void Player</h1>
        <p class="tagline">
          A lightweight, local-first music player for macOS with expressive UI modes and
          Apple-notarized releases.<br />No accounts, no telemetry.
        </p>
        <p class="supporting-note">
          A macOS-only player for enjoying local music files in a clean, focused library.
        </p>
        <div class="hero-actions" aria-label="Release links">
          <a class="primary-action" :href="latestReleaseUrl">Download latest notarized DMG</a>
          <a class="secondary-action" :href="releasesUrl">GitHub Releases</a>
          <a class="secondary-action" :href="youtubeUrl">YouTube demo</a>
        </div>
      </div>

      <figure class="hero-visual">
        <img :src="heroImage" alt="Void Player main interface screenshot" />
      </figure>
    </section>

    <section class="feature-section" aria-labelledby="features-title">
      <div class="section-heading">
        <p class="section-kicker">Why it is easy to trust</p>
        <h2 id="features-title">A release page that says what the app is, fast.</h2>
      </div>
      <div class="feature-grid">
        <article v-for="item in featureHighlights" :key="item.title" class="feature-card">
          <p>{{ item.eyebrow }}</p>
          <h3>{{ item.title }}</h3>
          <span>{{ item.copy }}</span>
        </article>
      </div>
    </section>

    <section class="demo-section" aria-labelledby="demo-title">
      <div class="demo-copy">
        <p class="section-kicker">Preview</p>
        <h2 id="demo-title">See the player in motion.</h2>
        <p>
          The demo keeps the release page self-contained while the primary download still points to
          the latest GitHub Release.
        </p>
      </div>
      <video :src="demoVideo" controls muted playsinline preload="metadata"></video>
    </section>

    <section class="mode-section" aria-labelledby="modes-title">
      <div class="section-heading">
        <p class="section-kicker">UI modes</p>
        <h2 id="modes-title">Switch the surface without changing the listening flow.</h2>
      </div>
      <div class="mode-grid">
        <article v-for="mode in modes" :key="mode.name" class="mode-card">
          <img :src="mode.image" :alt="`Void Player ${mode.name} mode screenshot`" />
          <div>
            <h3>{{ mode.name }}</h3>
            <p>{{ mode.copy }}</p>
          </div>
        </article>
      </div>
    </section>

    <footer class="site-footer">
      <span>Void Player</span>
      <a :href="latestReleaseUrl">Latest notarized DMG</a>
    </footer>
  </main>
</template>

<style>
:root {
  color: #151515;
  background: #f7f7f3;
  font-family:
    Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-width: 320px;
  background:
    linear-gradient(180deg, #ffffff 0%, #f7f7f3 44%, #eceee8 100%);
}

a {
  color: inherit;
}

.page-shell {
  width: min(1180px, calc(100% - 40px));
  margin: 0 auto;
  padding: 34px 0 28px;
  position: relative;
}

.github-corner {
  position: absolute;
  top: 34px;
  right: 0;
  color: #151515;
  opacity: 0.5;
  transition: opacity 0.2s;
}
.github-corner:hover {
  opacity: 1;
}

.hero-section {
  display: grid;
  grid-template-columns: minmax(0, 0.76fr) minmax(420px, 1fr);
  gap: 34px;
  align-items: center;
  min-height: min(760px, calc(100vh - 48px));
  padding: 34px 0 22px;
}

.hero-copy {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.release-label,
.section-kicker {
  margin: 0 0 13px;
  color: #28735f;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 0;
  text-transform: uppercase;
}

h1,
h2,
h3,
p {
  margin-top: 0;
}

h1 {
  margin-bottom: 17px;
  font-size: clamp(58px, 9vw, 116px);
  line-height: 0.86;
  letter-spacing: 0;
}

.tagline {
  max-width: 620px;
  margin-bottom: 16px;
  font-size: clamp(16px, 2vw, 24px);
  font-weight: 720;
  line-height: 1.04;
}

.supporting-note {
  max-width: 540px;
  margin-bottom: 26px;
  font-size: clamp(16px, 2vw, 24px);
  font-weight: 720;
  line-height: 1.04;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.primary-action,
.secondary-action {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 46px;
  border-radius: 8px;
  padding: 0 18px;
  font-size: 14px;
  font-weight: 760;
  text-decoration: none;
  transition:
    transform 180ms ease,
    border-color 180ms ease,
    background 180ms ease;
}

.primary-action {
  border: 1px solid #151515;
  background: #ff7a70;
  color: #151515;
}

.secondary-action {
  border: 1px solid #c9c9bd;
  background: rgba(255, 255, 255, 0.72);
  color: #25251f;
}

.primary-action:hover,
.secondary-action:hover {
  transform: translateY(-1px);
}

.secondary-action:hover {
  border-color: #151515;
}

.hero-visual {
  margin: 0;
  border: 1px solid #d9d9ce;
  border-radius: 8px;
  overflow: hidden;
  background: #151515;
}

.hero-visual img {
  display: block;
  width: 100%;
  aspect-ratio: 2786 / 2420;
  object-fit: cover;
  object-position: center top;
}

.feature-section,
.mode-section {
  padding: 80px 0 28px;
}

.section-heading {
  display: grid;
  grid-template-columns: minmax(160px, 0.35fr) minmax(0, 1fr);
  gap: 28px;
  align-items: start;
  margin-bottom: 24px;
}

.section-heading h2,
.demo-copy h2 {
  max-width: 780px;
  margin-bottom: 0;
  font-size: clamp(32px, 5vw, 58px);
  line-height: 0.98;
  letter-spacing: 0;
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 12px;
}

.feature-card,
.mode-card {
  border: 1px solid #d8d8cd;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.72);
}

.feature-card {
  min-height: 210px;
  padding: 20px;
}

.feature-card p {
  margin-bottom: 34px;
  color: #b95149;
  font-size: 12px;
  font-weight: 800;
  text-transform: uppercase;
}

.feature-card h3 {
  margin-bottom: 12px;
  font-size: 20px;
  line-height: 1.08;
}

.feature-card span,
.mode-card p,
.demo-copy p {
  color: #62625b;
  font-size: 14px;
  line-height: 1.55;
}

.demo-section {
  display: grid;
  grid-template-columns: minmax(240px, 0.42fr) minmax(0, 1fr);
  gap: 28px;
  align-items: center;
  padding: 80px 0 28px;
}

.demo-copy p {
  max-width: 420px;
  margin-top: 18px;
  margin-bottom: 0;
}

.demo-section video {
  display: block;
  width: 100%;
  border: 1px solid #d8d8cd;
  border-radius: 8px;
  background: #111;
}

.mode-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 14px;
}

.mode-card {
  overflow: hidden;
}

.mode-card img {
  display: block;
  width: 100%;
  aspect-ratio: 16 / 10;
  object-fit: cover;
  object-position: center top;
  border-bottom: 1px solid #d8d8cd;
  background: #171717;
}

.mode-card div {
  padding: 18px;
}

.mode-card h3 {
  margin-bottom: 8px;
  font-size: 22px;
}

.mode-card p {
  margin-bottom: 0;
}

.site-footer {
  display: flex;
  justify-content: space-between;
  gap: 16px;
  margin-top: 70px;
  padding: 20px 0 0;
  border-top: 1px solid #d8d8cd;
  color: #61615a;
  font-size: 13px;
}

.site-footer a {
  font-weight: 760;
  text-decoration: none;
}

@media (max-width: 940px) {
  .hero-section,
  .demo-section,
  .section-heading {
    grid-template-columns: 1fr;
  }

  .hero-section {
    gap: 26px;
    min-height: auto;
  }

  .feature-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 640px) {
  .page-shell {
    width: min(100% - 28px, 1180px);
    padding-top: 22px;
  }

  .hero-actions {
    width: 100%;
  }

  .primary-action,
  .secondary-action {
    width: 100%;
  }

  .feature-grid,
  .mode-grid {
    grid-template-columns: 1fr;
  }

  .feature-section,
  .demo-section,
  .mode-section {
    padding-top: 56px;
  }

  .site-footer {
    flex-direction: column;
  }
}
</style>
