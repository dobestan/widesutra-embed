# widesutra-embed

[![npm](https://img.shields.io/npm/v/widesutra-embed)](https://www.npmjs.com/package/widesutra-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/widesutra-embed)
[![Size](https://img.shields.io/badge/size-~5KB-green)](https://bundlephobia.com/package/widesutra-embed)

Embed WideSutra scripture widgets on any website. **Zero dependencies**, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and automatic daily teaching updates. Each widget includes a "Powered by WideSutra" backlink.

WideSutra covers the **Pali Canon (Tipitaka)** — **5 Nikayas** (collections), **5,326 suttas** (discourses), Pali language text with romanized transliteration, English translations, **Buddhist concepts glossary**, and teachings of the **historical Buddha (Siddhartha Gautama)** — all accessible via free public API.

> **Try the interactive widget builder at [widget.widesutra.com](https://widget.widesutra.com)**

<p align="center">
  <img src="demo.gif" alt="widesutra-embed demo — Buddhist sutra widget with Pali text and English translation, light/dark/sepia themes" width="800">
</p>

## Table of Contents

- [Quick Start](#quick-start)
- [What You Can Do](#what-you-can-do)
  - [Verse Card — Single Sutta Passage Display](#verse-card--single-sutta-passage-display)
  - [Chapter Card — Full Sutta with Navigation](#chapter-card--full-sutta-with-navigation)
  - [Comparison Card — Side-by-Side Teaching Comparison](#comparison-card--side-by-side-teaching-comparison)
  - [Verse of the Day — Auto-Updating Daily Widget](#verse-of-the-day--auto-updating-daily-widget)
  - [Search Box — Full-Text Pali Canon Search](#search-box--full-text-pali-canon-search)
- [Widget Options](#widget-options)
- [Themes](#themes)
- [CDN Options](#cdn-options)
- [Technical Details](#technical-details)
- [Learn More About Buddhist Sutras](#learn-more-about-buddhist-sutras)
- [WideHoly Scripture Family](#wideholy-scripture-family)
- [License](#license)

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-widesutra="verse" data-ref="dhp:1" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

That's it. The widget loads, fetches the passage from the WideSutra API, and renders it with full style isolation. References follow the collection/text format — `dhp:1` refers to Dhammapada verse 1, `mn:1` to Majjhima Nikaya Sutta 1.

## What You Can Do

The Pali Canon (Tipitaka — "Three Baskets") is the oldest complete collection of the Buddha's teachings, preserved in the Pali language by the Theravada tradition. It comprises the Vinaya Pitaka (monastic code), Sutta Pitaka (discourses), and Abhidhamma Pitaka (higher teachings). WideSutra focuses on the Sutta Pitaka's five Nikayas and the beloved Dhammapada — making 5,326 suttas accessible to developers building meditation apps, Dhamma study tools, or contemplative websites.

### Verse Card — Single Sutta Passage Display

A Verse Card renders a key passage from a sutta with Pali text and English translation. The Pali language — a Middle Indo-Aryan language closely related to Sanskrit — preserves the Buddha's teachings in their earliest written form. English translations come from scholars including Bhikkhu Bodhi (the most comprehensive academic translation) and Thanissaro Bhikkhu (freely available under open license).

| Collection | Code | Contents |
|------------|------|----------|
| Dhammapada | `dhp` | 423 verses on Dhamma principles |
| Digha Nikaya | `dn` | 34 long discourses |
| Majjhima Nikaya | `mn` | 152 middle-length discourses |
| Samyutta Nikaya | `sn` | 2,904 connected discourses |
| Anguttara Nikaya | `an` | 8,122 numerical discourses |
| Khuddaka Nikaya | `kn` | Minor works (Itivuttaka, Sutta Nipata, etc.) |

```html
<!-- Dhammapada 1:1 — Mind is the forerunner of all actions -->
<div data-widesutra="verse"
  data-ref="dhp:1"
  data-theme="light">
</div>

<!-- Majjhima Nikaya 22 — Alagaddupama Sutta (Snake Simile) with Pali text -->
<div data-widesutra="verse"
  data-ref="mn:22"
  data-translation="bodhi"
  data-show-original="true"
  data-theme="sepia">
</div>

<!-- Dhammapada 183 — The Teaching of the Buddhas, compact -->
<div data-widesutra="verse"
  data-ref="dhp:183"
  data-size="compact"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

**Available options for Verse Card:**

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-ref` | `"collection:number"` e.g. `dhp:1`, `mn:22` | required |
| `data-translation` | `bodhi`, `thanissaro`, `conze` | `bodhi` |
| `data-show-original` | `true`, `false` | `false` (shows Pali romanization) |
| `data-theme` | `light`, `dark`, `sepia` | `light` |
| `data-size` | `default`, `compact` | `default` |

Learn more: [Dhammapada — 423 verses](https://widesutra.com) · [Majjhima Nikaya Suttas](https://widesutra.com) · [Buddhist Concepts Glossary](https://widesutra.com)

### Chapter Card — Full Sutta with Navigation

A Chapter Card renders a complete sutta with structured sections and previous/next navigation. Suttas follow a standard narrative format: a setting (where the teaching occurred, who was present), the teaching itself (often including similes and dialogues), and a closing summary.

The Digha Nikaya's 34 long discourses include some of the most important texts in all of Buddhism — the Mahaparinibbana Sutta (DN 16) describes the Buddha's last days and passing, while the Samaññaphala Sutta (DN 2) outlines the fruits of the contemplative life.

```html
<!-- Dhammapada — Chapter 1 (Yamakavagga — Twin Verses, 20 verses) -->
<div data-widesutra="chapter"
  data-ref="dhp-chapter:1"
  data-theme="light">
</div>

<!-- Digha Nikaya 22 — Mahasatipatthana Sutta (Foundations of Mindfulness) -->
<div data-widesutra="chapter"
  data-ref="dn:22"
  data-translation="bodhi"
  data-theme="sepia">
</div>

<!-- Majjhima Nikaya 118 — Anapanasati Sutta (Mindfulness of Breathing) -->
<div data-widesutra="chapter"
  data-ref="mn:118"
  data-show-original="true"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

Learn more: [Browse Pali Canon — widesutra.com](https://widesutra.com) · [Digha Nikaya Long Discourses](https://widesutra.com) · [Sutta Nipata — Earliest Teachings](https://widesutra.com)

### Comparison Card — Side-by-Side Teaching Comparison

Compare two Buddhist teachings side by side — useful for showing how the same concept (anicca/impermanence, dukkha/suffering, anatta/non-self) is taught across different Nikayas, or for displaying parallel suttas that treat the same topic from different angles.

The Buddha gave different teachings to different audiences — sometimes emphasizing renunciation, sometimes lay practice, sometimes direct metaphysics. The Comparison Card highlights this pedagogical variety.

```html
<!-- Compare two impermanence teachings: Dhammapada 1 vs Samyutta Nikaya 22:95 -->
<div data-widesutra="compare"
  data-a="dhp:1"
  data-b="sn:22:95"
  data-theme="light">
</div>

<!-- Compare two descriptions of Nibbana: MN 26 vs Ud 8:1 -->
<div data-widesutra="compare"
  data-a="mn:26"
  data-b="dhp:203"
  data-show-original="true"
  data-theme="sepia">
</div>

<!-- Compare the Four Noble Truths stated in two suttas: SN 56:11 vs MN 141 -->
<div data-widesutra="compare"
  data-a="sn:56:11"
  data-b="mn:141"
  data-translation="bodhi"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

Learn more: [Samyutta Nikaya Connected Discourses](https://widesutra.com) · [Thematic Teaching Index](https://widesutra.com) · [Four Noble Truths References](https://widesutra.com)

### Verse of the Day — Auto-Updating Daily Widget

The Verse of the Day widget displays a curated sutta passage that changes automatically each day. Results are cached in localStorage and refresh at midnight UTC. The daily selection covers the Dhammapada's 423 verses plus key passages from each of the five Nikayas — 365 curated teachings suitable for daily contemplation.

```html
<!-- Teaching of the Day — full size, light theme -->
<div data-widesutra="votd" data-theme="light"></div>

<!-- Teaching of the Day — dark theme -->
<div data-widesutra="votd" data-theme="dark"></div>

<!-- Teaching of the Day — sepia, quiet contemplative tone -->
<div data-widesutra="votd" data-theme="sepia"></div>

<!-- Compact for narrow sidebars (passage excerpt + sutta reference) -->
<div data-widesutra="votd" data-theme="light" data-size="compact"></div>

<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

Learn more: [Daily Dhamma Teaching — widesutra.com](https://widesutra.com) · [Dhammapada Study Guide](https://widesutra.com) · [Meditation Suttas](https://widesutra.com)

### Search Box — Full-Text Pali Canon Search

Embed a full-text search box that queries all 5,326 suttas across the five Nikayas plus the Dhammapada. Results appear as the user types with collection, sutta number, and a highlighted snippet. Pali term search is fully supported — searching "dukkha" returns all occurrences across all collections without requiring special keyboard input.

```html
<!-- Default Pali Canon search -->
<div data-widesutra="search"
  data-placeholder="Search Buddhist sutras…"
  data-theme="light">
</div>

<!-- Pali-aware search placeholder -->
<div data-widesutra="search"
  data-placeholder="Search in English or Pali…"
  data-theme="sepia">
</div>

<!-- Dark theme search -->
<div data-widesutra="search"
  data-placeholder="Find a sutta or teaching…"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

Learn more: [Pali Canon Search — widesutra.com](https://widesutra.com) · [Buddhist Concepts Glossary](https://widesutra.com) · [API Search Endpoint](https://widesutra.com/developers/)

## Widget Options

All widget types share these common attributes:

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-widesutra` | `verse`, `chapter`, `compare`, `votd`, `search` | required | Widget type |
| `data-ref` | `"collection:number"` e.g. `dhp:1` | — | Sutta or verse reference |
| `data-a` | sutta reference | — | First passage for comparison |
| `data-b` | sutta reference | — | Second passage for comparison |
| `data-theme` | `light`, `dark`, `sepia` | `light` | Visual theme |
| `data-size` | `default`, `compact` | `default` | Compact suits sidebars under 300px |
| `data-translation` | `bodhi`, `thanissaro`, `conze` | `bodhi` | English translation |
| `data-show-original` | `true`, `false` | `false` | Show Pali romanized text |
| `data-placeholder` | any string | `"Search Sutra…"` | Placeholder for search widget |

## Themes

WideSutra widgets support 3 themes:

```html
<!-- Light — white background, dark text, amber/gold accent -->
<div data-widesutra="votd" data-theme="light"></div>

<!-- Dark — dark background, light text, gold accent -->
<div data-widesutra="votd" data-theme="dark"></div>

<!-- Sepia — warm tone, evokes the feel of aged palm-leaf manuscripts -->
<div data-widesutra="votd" data-theme="sepia"></div>
```

All themes are self-contained inside Shadow DOM — they never affect or inherit from your site's CSS.

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1/dist/embed.min.js"></script>
```

Pin to a specific version for production stability:

```html
<script src="https://cdn.jsdelivr.net/npm/widesutra-embed@1.0.1/dist/embed.min.js"></script>
```

### R2 CDN (widesutra.com hosted)

```html
<script src="https://cdn.widesutra.com/embed.min.js"></script>
```

### npm (for bundlers — Webpack, Vite, Rollup)

```bash
npm install widesutra-embed
```

```javascript
import 'widesutra-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site. Widgets are fully encapsulated.
- **Zero dependencies**: No jQuery, React, Vue, or any external library. Pure browser APIs only.
- **Pali rendering**: Romanized Pali (with diacritics like ā, ī, ū, ṭ, ḍ, ṇ, ṃ) renders correctly using system fonts.
- **System fonts**: No Google Fonts request — widgets use system font stack and load instantly.
- **CORS**: WideSutra API has CORS enabled for all origins — no proxy needed.
- **Caching**: Teaching of the Day cached in localStorage, refreshes daily at midnight UTC.
- **MutationObserver**: Works with dynamically added elements (React, Vue, Angular SPAs).
- **Bundle size**: ~5KB gzipped.
- **Accent color**: Gold/amber (`#D97706`) — matches the WideSutra brand.
- **API base**: `https://widesutra.com/api/v1/` — free, no authentication required.

## Learn More About Buddhist Sutras

- **Browse**: [Dhammapada — 423 verses](https://widesutra.com) · [Digha Nikaya — 34 long discourses](https://widesutra.com) · [Majjhima Nikaya — 152 middle discourses](https://widesutra.com) · [Samyutta Nikaya — 2,904 suttas](https://widesutra.com)
- **Study**: [Buddhist Concepts Glossary](https://widesutra.com) · [Pali Pronunciation Guide](https://widesutra.com) · [Four Noble Truths](https://widesutra.com) · [Noble Eightfold Path](https://widesutra.com)
- **Translators**: [Bhikkhu Bodhi Translations](https://widesutra.com) · [Thanissaro Bhikkhu](https://widesutra.com) · [Translation Comparison](https://widesutra.com)
- **Tools**: [Sutta Lookup](https://widesutra.com) · [Pali-English Dictionary](https://widesutra.com) · [Widget Builder](https://widget.widesutra.com)
- **API**: [REST API Docs](https://widesutra.com/developers/) · [OpenAPI Spec](https://widesutra.com/api/openapi.json)

## WideHoly Scripture Family

Part of [WideHoly](https://wideholy.com) — Scripture for everyone.

| Site | Domain | Scripture |
|------|--------|-----------|
| WideBible | [widebible.com](https://widebible.com) | 66 books, 31,102 verses, KJV/ASV/BBE/YLT, 1,833 people |
| WideQuran | [widequran.com](https://widequran.com) | 114 surahs, 6,236 ayahs, Arabic Uthmani + 5 translations |
| WideTorah | [widetorah.com](https://widetorah.com) | 24 books, 23,145 verses, Hebrew Masoretic + English, 54 parashot |
| WideGita | [widegita.com](https://widegita.com) | 18 chapters, 700 shlokas, Sanskrit Devanagari + 9 commentators |
| **WideSutra** | [widesutra.com](https://widesutra.com) | **5 Nikayas, 5,326 suttas, Pali + English, Dhammapada 423 verses** |
| WideHoly | [wideholy.com](https://wideholy.com) | 5 religions, 236,000+ scripture records, cross-religion comparison |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [WideHoly](https://wideholy.com).
