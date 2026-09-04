# Portofolio Pribadi (SCSS 7-1 Pattern)

Project ini merupakan implementasi konversi stylesheet portofolio ke **SCSS** menggunakan arsitektur modular **7-1 Pattern** dan compiler **Dart Sass**.

---

##  Struktur Folder

```text
├── index.html
├── style.css
├── package.json
└── scss/
    ├── abstracts/    # Variables, mixins, functions
    ├── vendors/      # Font eksternal
    ├── base/         # Reset, typography, base rules
    ├── layout/       # Header, footer, grid wrapper
    ├── components/   # Card, button, form
    ├── pages/        # Style khusus per section
    ├── themes/       # Dark mode
    └── main.scss     # Entry point utama SCSS
```

---

##  Cara Menjalankan

1. **Install dependensi:**
   ```bash
   npm install
   ```

2. **Kompilasi SCSS (Watch mode):**
   ```bash
   npm run watch:sass
   ```

3. **Build produksi (Minified CSS):**
   ```bash
   npm run build
   ```
