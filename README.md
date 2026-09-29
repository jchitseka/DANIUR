# Agrivana — Organic Farming Framer Template

Static recreation of the Agrivana Organic Farming Framer template (agrivana.framer.ai), reorganized into a clean, self-contained project structure. Appearance, layout, responsiveness, and interactions are preserved exactly as in the original.

## Structure

```
agrivana/
├── index.html                  Entry page (hand-rebuilt head, framework body preserved verbatim)
├── assets/
│   ├── css/
│   │   ├── fonts.css            Google Fonts @font-face blocks (remote origins kept)
│   │   ├── framer.css           Main Framer-styled SSR stylesheet (580 rules, 42 media queries)
│   │   └── framer-editorbar.css Styles for the editor bar iframe container
│   ├── js/
│   │   ├── framer-animator.js   Framer animation runtime (exposes global `animator`)
│   │   ├── tracking.js          Analytics beacon (data-fid/data-no-nt payload preserved)
│   │   └── framer/
│   │       └── framer-main.esm.mjs   Frameworks entry module
│   ├── images/                  Renamed from opaque hashes to semantic names
│   │   └── logos/               Brand logo + partner logos (SVG)
│   └── icons/                   Arrow navigation icons (PNG)
├── framer/editor/
│   ├── edit.html                Editor bar frame
│   ├── editorbar.mjs            Editor bar module
│   └── bootstrap.js             Editor bootstrap (sets window.bootstrap)
├── favicon/
│   ├── favicon.png              32px favicon
│   └── apple-touch-icon.png     180px touch icon
└── README.md
```

## Notes

- The page body is the original Framer server-rendered output and is preserved as-is. Its markup, class names, inline SVG sprite, animation/breakpoint declarations, and script order are functional and must not be reformatted.
- Media files were renamed from Framer hash names (e.g. `NAI8dDt2AvNHVhdB7a5DaOreC6M.jpg`) to semantic names (`assets/images/hero-bg.jpg`); only local `src` references were rewritten.
- `srcset`, `og:image`, `twitter:image`, and font `url()` references intentionally keep their framerusercontent.com / fonts.gstatic.com URLs, matching original loading behavior.
- The framework entry (`framer-main.esm.mjs`) uses relative imports to Framer runtime modules that are hosted on the Framer CDN and are not bundled locally. The page renders and animates fully from static content; full client-side hydration requires those CDN modules, as in the original.
- Current date placeholder: the page was saved from the live site and is a static snapshot.