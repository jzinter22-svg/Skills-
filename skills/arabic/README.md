# Arabic (RTL / Arabic Typography & Internationalization) Skills & Resources

Curated, verified open-source resources for Arabic typography and right-to-left (RTL) web internationalization: verified font families for Arabic/Latin bilingual UIs, RTL layout tooling, and mature Arabic NLP libraries. Use these when building an Arabic or mixed Arabic+Latin interface, converting an LTR stylesheet to RTL, or processing Arabic text programmatically.

## Best Repositories

### [google/fonts — Cairo](https://github.com/Gue3bara/Cairo) ([upstream](https://github.com/google/fonts/tree/main/ofl/cairo))
- **Stars:** ~193 (as of 2026-07-13, upstream `Gue3bara/Cairo` repo)
- **License:** OFL-1.1
- **Last updated:** 2023-03-06 (stable/mature; distributed live via Google Fonts)

Cairo is a contemporary Arabic + Latin typeface based on the Kufi calligraphic style, extending the Latin family Titillium Web to Arabic. A very popular geometric sans for Arabic UI and headline text.

**Installation:**
```bash
npm install @fontsource/cairo
```

**Usage example:**
```css
@import "@fontsource/cairo/400.css";
@import "@fontsource/cairo/700.css";

body { font-family: "Cairo", sans-serif; }
```

### [googlefonts/tajawal](https://github.com/googlefonts/tajawal)
- **Stars:** ~60 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** repo archived 2021 (font is stable/mature; current canonical copy lives in `google/fonts/ofl/tajawal`)

Tajawal is a low-contrast, modern geometric Arabic sans-serif by Boutros Fonts, matched with a Latin companion. Frequently used for Arabic marketing sites and dashboards needing a clean, neutral voice.

**Installation:**
```bash
npm install @fontsource/tajawal
```

**Usage example:**
```css
@import "@fontsource/tajawal/500.css";

body { font-family: "Tajawal", sans-serif; }
```

### [IBM/plex](https://github.com/IBM/plex) (IBM Plex Sans Arabic)
- **Stars:** ~11,495 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** actively maintained, pushed 2026-06-12

IBM's corporate type system, which includes a dedicated Sans Arabic cut designed to pair cleanly with the Latin IBM Plex Sans. Excellent choice when a product already uses IBM Plex for Latin text and needs a harmonized Arabic companion.

**Installation:**
```bash
npm install @ibm/plex-sans-arabic
```

**Usage example:**
```css
@font-face {
  font-family: 'IBM Plex Sans Arabic';
  src: url('@ibm/plex-sans-arabic/fonts/complete/woff2/IBMPlexSansArabic-Regular.woff2') format('woff2');
  font-weight: 400;
}
body { font-family: 'IBM Plex Sans Arabic', 'IBM Plex Sans', sans-serif; }
```

### [notofonts/arabic](https://github.com/notofonts/arabic) (Noto Sans Arabic & Noto Naskh Arabic)
- **Stars:** ~30 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** actively maintained, pushed 2026-02-26

The official build/QA repository for Google/Noto's Arabic families: Noto Sans Arabic (unmodulated, UI-friendly) and Noto Naskh Arabic (traditional Naskh calligraphic style, better for long-form reading). Part of the Noto project's goal of universal Unicode script coverage with zero "tofu" (missing-glyph boxes).

**Installation:**
```bash
npm install @fontsource/noto-sans-arabic @fontsource/noto-naskh-arabic
```

**Usage example:**
```css
@import "@fontsource/noto-naskh-arabic/400.css";

.quran-text, .long-form-arabic {
  font-family: "Noto Naskh Arabic", serif;
  line-height: 1.9; /* Naskh needs generous line-height for diacritics */
}
```

### [aliftype/amiri](https://github.com/aliftype/amiri)
- **Stars:** ~469 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** actively maintained, pushed 2026-04-25

Amiri is a classical Naskh revival typeface based on the early-20th-century Bulaq Press typeface, by type designer Khaled Hosny. Considered one of the highest-quality open-source Arabic text faces for long-form/literary content, with extensive OpenType feature support for Quranic and classical typesetting.

**Installation:**
```bash
npm install @fontsource/amiri
```

**Usage example:**
```css
@import "@fontsource/amiri/400.css";

body.classical-arabic {
  font-family: "Amiri", serif;
  font-feature-settings: "liga", "calt";
}
```

### [ThomasJockin/readexpro](https://github.com/ThomasJockin/readexpro) (Readex Pro)
- **Stars:** ~548 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** 2025-02-14

Readex Pro is the Arabic/world-script expansion of Lexend, a variable font family whose design was empirically tested to improve reading proficiency. Good for accessibility-focused or educational Arabic+Latin products.

**Installation:**
```bash
npm install @fontsource-variable/readex-pro
```

**Usage example:**
```css
@import "@fontsource-variable/readex-pro";

body { font-family: "Readex Pro Variable", sans-serif; }
```

### [Gue3bara/Alexandria](https://github.com/Gue3bara/Alexandria)
- **Stars:** ~24 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** 2022-12-05 (stable/mature; distributed live via Google Fonts)

Alexandria is the Arabic companion to Montserrat, a 9-weight variable geometric sans covering Thin to Black. Best when a design already uses Montserrat for Latin and needs a matching Arabic weight range for headlines through body copy.

**Installation:**
```bash
npm install @fontsource-variable/alexandria
```

**Usage example:**
```css
@import "@fontsource-variable/alexandria";

h1 { font-family: "Alexandria Variable", sans-serif; font-weight: 800; }
```

### [googlefonts/changa-vf](https://github.com/googlefonts/changa-vf) (Changa)
- **Stars:** ~23 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** repo archived 2021 (font is stable/mature; current canonical copy lives in `google/fonts/ofl/changa`)

Changa is a display/headline sans-serif by Eduardo Tunni with Arabic drawn in collaboration with Mohamed Gaber (also the designer of Cairo and Alexandria). Best suited to bold headlines and titles rather than long body text.

**Installation:**
```bash
npm install @fontsource/changa
```

**Usage example:**
```css
@import "@fontsource/changa/700.css";

h1, h2 { font-family: "Changa", sans-serif; }
```

### [MohammadYounes/rtlcss](https://github.com/MohammadYounes/rtlcss)
- **Stars:** ~1,706 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, pushed 2025-02-18

The most widely used framework for mechanically flipping an LTR CSS file into an RTL one (`left`→`right`, `margin-left`→`margin-right`, etc.), with a plugin ecosystem (webpack, PostCSS, Gulp). Best when you maintain a large legacy LTR codebase and need automated RTL output rather than hand-writing logical properties everywhere. A closely related, actively updated alternative is [postcss-rtlcss](https://github.com/elchininet/postcss-rtlcss), which wraps rtlcss as a PostCSS plugin.

**Installation:**
```bash
npm install rtlcss --save-dev
```

**Usage example:**
```bash
npx rtlcss style.css style.rtl.css
```
```css
/* input (style.css) */
.card { margin-left: 16px; text-align: left; }
/* output (style.rtl.css) */
.card { margin-right: 16px; text-align: right; }
```

### [linuxscout/pyarabic](https://github.com/linuxscout/pyarabic)
- **Stars:** ~484 (as of 2026-07-13)
- **License:** GPL-3.0
- **Last updated:** actively maintained, pushed 2026-01-16

A mature Python library for Arabic text processing: diacritic (tashkeel) stripping/handling, letter normalization, tokenization, and other string-level operations specific to Arabic script. Useful as a lightweight preprocessing step before search indexing or NLP.

**Installation:**
```bash
pip install pyarabic
```

**Usage example:**
```python
import pyarabic.araby as araby

text = "الْعَرَبِيَّة"
print(araby.strip_tashkeel(text))  # -> "العربية"
```

### [CAMeL-Lab/camel_tools](https://github.com/CAMeL-Lab/camel_tools)
- **Stars:** ~563 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, pushed 2026-06-08

A full Arabic NLP suite from NYU Abu Dhabi's CAMeL Lab: morphological analysis/disambiguation, dialect identification, POS tagging, named-entity recognition, and sentiment analysis. The most complete and academically rigorous open-source toolkit for Arabic NLP, including Modern Standard Arabic and dialectal variants.

**Installation:**
```bash
pip install camel-tools
camel_data -i all   # downloads required model/data packages
```

**Usage example:**
```python
from camel_tools.tokenizers.word import simple_word_tokenize
from camel_tools.disambig.mle import MLEDisambiguator

tokens = simple_word_tokenize("كتب الطالب الدرس")
mle = MLEDisambiguator.pretrained()
disambig = mle.disambiguate(tokens)
```

## Font Pairing & RTL Best Practices

**Pairing an Arabic font with a Latin font.** Don't rely on the browser's default font-matching fallback for mixed-script text — explicitly stack a paired Arabic + Latin family so weights and x-heights feel consistent:

```css
:root {
  /* Cairo (Arabic) paired with its Latin-friendly companion */
  --font-ui: "Cairo", "Inter", system-ui, sans-serif;
  /* Amiri (Arabic Naskh) paired with a classical Latin serif for long-form reading */
  --font-reading: "Amiri", "Noto Naskh Arabic", Georgia, serif;
}

body { font-family: var(--font-ui); }
article, .prose { font-family: var(--font-reading); }
```

Good verified pairings from the fonts above:
- **Cairo + Inter** — UI/product text, both geometric sans.
- **IBM Plex Sans Arabic + IBM Plex Sans** — designed together by IBM as a single system.
- **Alexandria + Montserrat** — Alexandria was explicitly designed as Montserrat's Arabic companion.
- **Amiri + Noto Naskh Arabic** or a Latin serif — long-form/literary reading.

**Direction handling with `dir="rtl"`.** Set direction at the document or container level rather than fighting it with CSS floats:

```html
<html lang="ar" dir="rtl">
  <body>
    <!-- Force a specific sub-tree back to LTR, e.g. an embedded code block or phone number -->
    <span dir="ltr">+1 (555) 123-4567</span>
  </body>
</html>
```

**Use CSS logical properties instead of physical left/right.** This is the modern, maintainable alternative to rtlcss transforms — one stylesheet works for both directions automatically when `dir` changes:

```css
.card {
  /* Instead of margin-left / margin-right */
  margin-inline-start: 1rem;
  margin-inline-end: 1.5rem;

  /* Instead of padding-left / padding-right */
  padding-inline: 1rem 2rem;

  /* Instead of border-left */
  border-inline-start: 2px solid var(--accent);

  /* Instead of text-align: left */
  text-align: start;

  /* Instead of left: 0 in absolute positioning */
  inset-inline-start: 0;
}
```

**Line-height and vertical rhythm for Arabic script.** Arabic diacritics (tashkeel), ascenders, and connected letterforms typically need more vertical breathing room than Latin text at the same font size:

```css
:lang(ar) {
  line-height: 1.7;      /* vs. ~1.4-1.5 typical for Latin body text */
  letter-spacing: 0;      /* never add letter-spacing to Arabic — it breaks cursive joining */
}

:lang(ar) h1, :lang(ar) h2 {
  line-height: 1.4;       /* headlines can be tighter than body copy */
}
```

**Mirroring vs. not mirroring icons.** Directional icons (arrows, chevrons, "back/forward") should flip in RTL; symmetric icons (search, settings gear) should not:

```css
[dir="rtl"] .icon-arrow-forward {
  transform: scaleX(-1);
}
```

**Automated LTR→RTL conversion for legacy CSS.** When you can't yet migrate a large stylesheet to logical properties, use rtlcss or postcss-rtlcss as a build step to generate an RTL stylesheet from your existing LTR one, rather than maintaining two by hand.

## Notes

- Several of the individually-listed font repos (Tajawal, Changa) are archived on GitHub because font development moved into the `google/fonts` monorepo — this reflects Google Fonts' standard workflow, not abandonment; the fonts remain actively served and are considered stable/mature.
- `pyarabic` is GPL-3.0, which is copyleft — check license compatibility before embedding it in a proprietary product; `camel_tools` (MIT) has no such restriction.
- Always test Arabic text rendering with real diacritics (tashkeel) and connected letterforms, not just isolated characters — font metrics and `line-height` bugs often only appear with full words.
- Prefer `logical properties` (`margin-inline-start`, `inset-inline-end`, etc.) for new code; reserve `rtlcss`/`postcss-rtlcss` for retrofitting existing LTR-only stylesheets you don't want to rewrite by hand.

## License Summary

| Repository | License |
|---|---|
| Gue3bara/Cairo | OFL-1.1 |
| googlefonts/tajawal | OFL-1.1 |
| IBM/plex (IBM Plex Sans Arabic) | OFL-1.1 |
| notofonts/arabic (Noto Sans/Naskh Arabic) | OFL-1.1 |
| aliftype/amiri | OFL-1.1 |
| ThomasJockin/readexpro (Readex Pro) | OFL-1.1 |
| Gue3bara/Alexandria | OFL-1.1 |
| googlefonts/changa-vf (Changa) | OFL-1.1 |
| MohammadYounes/rtlcss | MIT |
| linuxscout/pyarabic | GPL-3.0 |
| CAMeL-Lab/camel_tools | MIT |
