# Tugas Pertemuan 4: Konversi CSS ke SCSS (7-1 Pattern)

Dokumentasi implementasi konversi stylesheet portofolio dari CSS native ke SCSS modular dengan arsitektur **7-1 pattern** dan fitur modern Sass (`@use`, `@forward`, mixins, loops, maps, nesting).

---

## 🎯 Pemenuhan Requirements Tugas

| No | Requirement | Implementasi pada Proyek | Lokasi File |
|:---|:---|:---|:---|
| 1 | **Konversi CSS existing ke SCSS** | Seluruh styling portofolio dikonversi penuh ke SCSS modular. | `scss/**/*.scss` |
| 2 | **Variables (Colors & Spacing)** | Token warna (`$clr-primary`, `$clr-bg`, dll.) dan skala `$spacing-xs` hingga `$spacing-3xl`. | [`_variables.scss`](scss/abstracts/_variables.scss) |
| 3 | **Nesting maksimal 3 level** | Penataan hierarki BEM clean & strictly terbatasi maksimal 2–3 level kedalaman. | [`_card.scss`](scss/components/_card.scss), [`_form.scss`](scss/components/_form.scss), dll. |
| 4 | **Minimal 3 Reusable Mixins** | `@mixin flex-box`, `@mixin card-style`, `@mixin respond-to`, dan `@mixin transition`. | [`_mixins.scss`](scss/abstracts/_mixins.scss) |
| 5 | **Struktur 7-1 Pattern (Partials)** | Folder modular lengkap: `abstracts/`, `vendors/`, `base/`, `layout/`, `components/`, `pages/`, `themes/`. | `scss/` |
| 6 | **Wajib `@use` (No `@import`)** | Semua modul di-load menggunakan `@use` & `@forward` tanpa `@import` Sass lama. | [`main.scss`](scss/main.scss) & semua `_index.scss` |
| 7 | **Minimal 1 `@each` / `@for` loop** | `@each` untuk modifier card keahlian & `@for` loop untuk staggered animation delay. | [`_skills.scss`](scss/pages/_skills.scss) |
| 8 | **Compile dengan Dart SASS / Vite** | Build setup menggunakan Dart Sass (`sass`) via `package.json` scripts. | [`package.json`](package.json) |

---

## 📂 Struktur Arsitektur 7-1 Pattern

```text
TugasWeb-Pertemuan4-Scss/
├── index.html
├── package.json
├── package-lock.json
├── style.css                  # Output kompilasi Dart Sass
├── style.css.map              # Source map untuk debugging browser
├── yahya.jpeg
└── scss/
    ├── abstracts/
    │   ├── _functions.scss    # Helper functions (rem converter)
    │   ├── _index.scss        # Forwarding abstracts
    │   ├── _mixins.scss       # Reusable mixins (flex-box, card-style, respond-to, transition)
    │   └── _variables.scss    # Color palette, spacing system, breakpoints, maps
    ├── base/
    │   ├── _base.scss         # CSS custom properties root, html, body, links
    │   ├── _index.scss        # Forwarding base
    │   ├── _reset.scss        # Universal box-sizing, margin/padding reset
    │   └── _typography.scss   # Font family, base text, font sizes & headings
    ├── components/
    │   ├── _button.scss       # Form buttons & CTA button styling
    │   ├── _card.scss         # Profile figure, skill cards, project cards, aside
    │   ├── _form.scss         # Form inputs, textarea, color picker, range slider
    │   └── _index.scss        # Forwarding components
    ├── layout/
    │   ├── _footer.scss       # Footer layout & copyright text
    │   ├── _grid.scss         # Page wrapper grid & section spacing
    │   ├── _header.scss       # Site header & main navigation layout
    │   └── _index.scss        # Forwarding layout
    ├── pages/
    │   ├── _about.scss        # About section specific layout & typography
    │   ├── _contact.scss      # Contact section intro styling
    │   ├── _index.scss        # Forwarding pages
    │   ├── _projects.scss     # Projects grid & aside column layout
    │   └── _skills.scss       # Skills section flex layout + @each & @for loops
    ├── themes/
    │   ├── _dark.scss         # Dark mode media prefers-color-scheme tokens
    │   └── _index.scss        # Forwarding themes
    ├── vendors/
    │   ├── _fonts.scss        # Google Fonts import
    │   └── _index.scss        # Forwarding vendors
    └── main.scss              # Master entry point mengimpor semua modul via @use
```

---

## 🚀 Cara Menjalankan Kompilasi SCSS

Pastikan Node.js sudah terpasang, lalu jalankan perintah berikut di terminal:

### 1. Compile SCSS Sekali Jalan (Expanded Mode + Source Map)
```bash
npm run compile:sass
```

### 2. Auto-Compile saat File SCSS Berubah (Watch Mode)
```bash
npm run watch:sass
```

### 3. Build Versi Produksi (Compressed Minified CSS)
```bash
npm run build
```
