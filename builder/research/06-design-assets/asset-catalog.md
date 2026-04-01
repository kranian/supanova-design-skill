# Design Asset Catalog - Cheolmoksu Landing Page

> Premium visual asset resources for steel house construction specialist landing page.
> Researched: 2026-04-01

---

## 1. Icon Sets (Free, Open Source)

### Lucide Icons (Recommended Primary)
- **URL**: https://lucide.dev/icons/
- **License**: ISC License (free for commercial use)
- **Count**: 1,368+ icons
- **Format**: SVG, React/Vue/Svelte components
- **Construction-relevant icons**:
  - `hammer` - mallet, build, construction
  - `wrench` - settings, toolbox, build
  - `construction` - roadwork, maintenance, barricade
  - `house` - home, building, residence, architecture
  - `house-plug` - energy-efficient home
  - `building` - organisation, commercial
  - `hard-hat`, `ruler`, `shield-check`, `truck`
- **Why**: Clean line style fits premium dark theme. Native Tailwind CSS integration. Tree-shakeable.
- **CDN**: `https://unpkg.com/lucide@latest`

### Heroicons
- **URL**: https://heroicons.com/
- **License**: MIT License (free for commercial use)
- **Count**: 300+ icons in outline/solid/mini styles
- **Format**: SVG, React/Vue components
- **Why**: Created by Tailwind CSS team. Perfect visual consistency with Tailwind projects.
- **CDN**: `https://unpkg.com/@heroicons/react@latest`

### Phosphor Icons
- **URL**: https://phosphoricons.com/
- **License**: MIT License (free for commercial use)
- **Count**: 6,000+ icons in 6 weights (thin, light, regular, bold, fill, duotone)
- **Format**: SVG, React/Vue/Flutter/Figma
- **Why**: Largest collection. Duotone style adds visual richness to dark themes. Best for icon-heavy sections like feature grids.

### Recommended Combination
- **Primary**: Lucide for UI navigation and common elements
- **Accent**: Phosphor Duotone for feature cards and hero section highlights
- **Fallback**: Heroicons for any missing glyphs

---

## 2. Stock Photos

### Completely Free (No Attribution Required)

#### Unsplash
- **URL**: https://unsplash.com/s/photos/steel-construction
- **License**: Unsplash License (free for commercial use, no attribution required)
- **Search terms**: "steel construction", "steel building", "metal fabrication", "welding sparks", "steel frame house"
- **Quality**: High-resolution, professional photography
- **Best for**: Hero backgrounds, full-bleed sections

#### Pexels
- **URL**: https://www.pexels.com/search/steel-construction/
- **License**: Pexels License (free for commercial use, no attribution required)
- **Search terms**: "steel frame", "construction welding", "metal structure", "industrial building"
- **Count**: 60,000+ construction photos
- **Best for**: Process/timeline section images

#### Pixabay
- **URL**: https://pixabay.com/images/search/steel-construction/
- **License**: Pixabay License (free for commercial use, no attribution required)
- **Search terms**: "steel house", "welding", "metal fabrication", "construction worker"
- **Best for**: Background textures, detail shots

### Freemium (Free with Attribution / Paid Premium)

#### Freepik
- **URL**: https://www.freepik.com/free-photos-vectors/steel-welding
- **License**: Free with attribution, Premium without
- **Why**: Largest collection of welding and fabrication vectors and photos
- **Best for**: Supplementary images, vector overlays

#### Dreamstime
- **URL**: https://www.dreamstime.com/photos-images/steel-fabrication.html
- **License**: Royalty-free, some free editorial use
- **Count**: 19,000+ steel fabrication photos
- **Best for**: Specific niche shots (steel house framing, H-beam assembly)

### Recommended Photo Strategy
1. **Hero**: Unsplash steel construction with dark overlay (70% opacity)
2. **Process Section**: Pexels welding/fabrication action shots
3. **Gallery**: Mix Unsplash + Pexels for variety
4. **Background Texture**: Pixabay steel/metal close-ups with CSS blur

---

## 3. Background Patterns & Textures

### Pure CSS Patterns

#### MagicPattern CSS Backgrounds
- **URL**: https://www.magicpattern.design/tools/css-backgrounds
- **License**: Free for commercial use
- **Format**: Pure CSS (no image files needed)
- **Best patterns**: Grid lines (blueprint feel), diagonal lines (industrial), dots (subtle texture)
- **Performance**: Zero HTTP requests, lightweight

#### FreeFrontend CSS Patterns
- **URL**: https://freefrontend.com/css-background-patterns/
- **License**: Various (check individual patterns)
- **Count**: 232 CSS patterns
- **Best for**: Section dividers, card backgrounds

#### DevSnap CSS Patterns
- **URL**: https://devsnap.me/css-background-patterns
- **License**: Free and open source
- **Count**: 65+ patterns with live demos

### Texture Assets (Vector/Image)

#### Vecteezy Blueprint Textures
- **URL**: https://www.vecteezy.com/free-vector/blueprint-texture
- **License**: Free with attribution (Vecteezy License)
- **Count**: 2,984 blueprint texture vectors
- **Format**: SVG, AI, EPS
- **Best for**: Blueprint-style section backgrounds

#### Vecteezy Metal/Steel Textures
- **URL**: https://www.vecteezy.com/free-vector/metal-texture
- **License**: Free with attribution
- **Count**: 48,851 metal texture vectors
- **Best for**: Subtle steel-grain overlays

#### Unsplash Metal Textures
- **URL**: https://unsplash.com/s/photos/metal-texture
- **License**: Free, no attribution
- **Best for**: Full-bleed dark textured backgrounds

### Recommended Pattern Strategy
```css
/* Blueprint grid overlay for hero section */
.hero-pattern {
  background-image:
    linear-gradient(rgba(30, 64, 175, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(30, 64, 175, 0.03) 1px, transparent 1px);
  background-size: 40px 40px;
}

/* Steel grain texture for cards */
.steel-texture {
  background-image: url('data:image/svg+xml,...'); /* inline SVG noise */
  opacity: 0.02;
}

/* Diagonal lines for accent sections */
.industrial-lines {
  background-image: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 10px,
    rgba(255,255,255,0.02) 10px,
    rgba(255,255,255,0.02) 11px
  );
}
```

---

## 4. CSS Animation Libraries

### GSAP + ScrollTrigger (Recommended Primary)
- **URL**: https://gsap.com/
- **License**: Free for commercial use (as of 2024 license change)
- **Size**: ~25KB core + ~10KB ScrollTrigger
- **Features**:
  - Hardware-accelerated scroll animations
  - Timeline-based sequencing
  - Pin elements during scroll
  - Scrub animations to scroll position
- **Best for**: Hero parallax, process timeline reveals, number counters
- **CDN**: `https://cdn.jsdelivr.net/npm/gsap@3/dist/gsap.min.js`
- **ScrollTrigger CDN**: `https://cdn.jsdelivr.net/npm/gsap@3/dist/ScrollTrigger.min.js`

### AOS (Animate on Scroll)
- **URL**: https://michalsnik.github.io/aos/
- **License**: MIT (free for commercial use)
- **Size**: ~13KB
- **Features**: Simple data-attribute API, 20+ preset animations
- **Best for**: Quick fade-in/slide-up reveals for cards and text
- **Caveat**: Development slowed; works best with vanilla HTML/JS (not ideal for Next.js)
- **CDN**: `https://cdn.jsdelivr.net/npm/aos@2/dist/aos.css`

### Lenis (Smooth Scroll)
- **URL**: https://lenis.darkroom.engineering/
- **License**: MIT (free for commercial use)
- **Features**: Smooth momentum scrolling, industry standard in 2026
- **Best for**: Premium smooth scroll feel, pairs perfectly with GSAP ScrollTrigger
- **CDN**: `https://cdn.jsdelivr.net/npm/lenis@latest`

### Motion (Framer Motion)
- **URL**: https://motion.dev/
- **License**: MIT (free for commercial use)
- **Features**: React-native scroll animations, `whileInView`, `useScroll`
- **Best for**: React/Next.js projects with component-level animation control
- **Note**: Only relevant if building with React framework

### CSS Scroll-Driven Animations (Native)
- **URL**: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations
- **License**: Native browser API (no library needed)
- **Support**: Chrome 115+, Edge 115+, Firefox 110+ (partial)
- **Best for**: Simple parallax and progress indicators without JavaScript

### Recommended Animation Stack
1. **Lenis** for smooth scrolling baseline
2. **GSAP + ScrollTrigger** for hero parallax, timeline reveals, counters
3. **AOS** for simple card/text fade-ins (if not using React)
4. **CSS native** for progress bars and subtle transforms

---

## 5. Tailwind CSS Component Libraries

### Tailwind Plus (Official, Premium)
- **URL**: https://tailwindcss.com/plus
- **License**: Commercial ($299 one-time)
- **Components**: 500+ professionally designed components
- **Dark theme**: Full support
- **Best for**: Reference quality, pixel-perfect components

### daisyUI (Free, Recommended)
- **URL**: https://daisyui.com/
- **License**: MIT (free for commercial use)
- **Components**: 55+ components with Tailwind v4 support
- **Dark theme**: Built-in via CSS variables, 32 themes including `dark`, `luxury`, `business`
- **Best for**: Rapid prototyping with instant dark mode. `luxury` and `business` themes suit construction brands.

### Flowbite (Free + Pro)
- **URL**: https://flowbite.com/
- **License**: MIT (free core), Commercial (pro)
- **Components**: 450+ UI components
- **Dark theme**: Built-in dark mode support
- **Best for**: Complete UI component coverage with dark mode toggle

### Tailgrids (Free + Pro)
- **URL**: https://tailgrids.com/
- **License**: Free tier available, Pro for full access
- **Components**: 600+ components
- **Dark theme**: Built-in light/dark themes aligned with system preferences
- **Best for**: Landing page blocks (hero, features, pricing, testimonials)

### FlyonUI
- **URL**: https://flyonui.com/
- **License**: Free (MIT)
- **Features**: Tailwind CSS component library with theme support
- **Best for**: Alternative to daisyUI with different design language

### Recommended Approach
- **Pure Tailwind + CDN** for the Cheolmoksu landing page (no framework dependency)
- Reference **daisyUI `luxury` theme** color tokens for dark premium feel
- Use **Tailgrids** landing page blocks as structural inspiration
- Keep it framework-free: pure HTML + Tailwind CDN for maximum portability

---

## 6. Font Pairings (Korean + English)

### Primary Sans-Serif: Pretendard

#### Pretendard
- **URL**: https://github.com/orioncactus/pretendard
- **License**: SIL Open Font License (free for commercial use)
- **Weights**: 9 weights (Thin to Black)
- **Features**: Built on Inter + Source Han Sans + M PLUS 1p. Optimized CJK rendering.
- **CDN**: `https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css`
- **Best for**: Body text, UI elements, navigation
- **Korean name**: 프리텐다드

### Serif Pairing Options

#### Noto Serif KR (Recommended)
- **URL**: https://fonts.google.com/noto/specimen/Noto+Serif+KR
- **License**: SIL Open Font License (free for commercial use)
- **Weights**: 7 weights (ExtraLight to Black)
- **Features**: Full Korean coverage, harmonious with Latin serif
- **CDN**: Google Fonts (`fonts.googleapis.com`)
- **Best for**: Headlines, section titles, brand statement
- **Why**: Most complete Korean serif. Excellent contrast with Pretendard body.

#### KoPub Batang
- **URL**: https://www.kopus.org/biz-electronic-font2/
- **License**: Free for commercial use (Korea Publishers Society)
- **Weights**: Light, Medium, Bold
- **Features**: Government-backed, optimized for reading at text sizes
- **Best for**: Alternative to Noto Serif KR for a more traditional feel

### English Accent Fonts

#### Playfair Display
- **URL**: https://fonts.google.com/specimen/Playfair+Display
- **License**: SIL Open Font License
- **Best for**: English headlines paired with Korean serif
- **Style**: High-contrast transitional serif, luxurious feel

#### DM Serif Display
- **URL**: https://fonts.google.com/specimen/DM+Serif+Display
- **License**: SIL Open Font License
- **Best for**: Short English brand phrases, numbers
- **Style**: Low-contrast serif, modern and warm

### Recommended Font Stack
```css
/* Headlines / Brand */
font-family: 'Noto Serif KR', 'Playfair Display', Georgia, serif;

/* Body / UI */
font-family: 'Pretendard Variable', 'Pretendard', -apple-system, BlinkMacSystemFont,
  system-ui, Roboto, 'Helvetica Neue', 'Segoe UI', 'Apple SD Gothic Neo',
  'Noto Sans KR', 'Malgun Gothic', 'Apple Color Emoji', 'Segoe UI Emoji',
  'Segoe UI Symbol', sans-serif;

/* Accent Numbers / English Brand */
font-family: 'DM Serif Display', 'Noto Serif KR', serif;
```

### Font Loading Strategy (CDN)
```html
<!-- Pretendard Variable -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.min.css" />

<!-- Noto Serif KR (weights 400, 700) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@400;700&display=swap" rel="stylesheet">

<!-- Playfair Display (weight 700) -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
```

---

## 7. Color Palettes

### Palette Generators

#### Coolors
- **URL**: https://coolors.co/
- **License**: Free tier available
- **Features**: Spacebar to generate, lock colors, export as PNG/SVG/code
- **Industrial palettes**: https://coolors.co/palettes/popular/industrial

#### ColorMagic
- **URL**: https://colormagic.app/palette/explore/metal
- **License**: Free
- **Features**: AI-powered palette generation, metal/steel category
- **Best for**: Steel and metal-specific palettes with hex codes

#### Realtime Colors
- **URL**: https://www.realtimecolors.com/
- **License**: Free
- **Features**: Preview palette on a live website template instantly
- **Best for**: Testing dark theme palettes in context

### Curated Industrial Palettes

#### Steel Blue + Safety Orange (Recommended Primary)
```
--steel-950:    #0a0f1a    /* Deep background */
--steel-900:    #111827    /* Card background */
--steel-800:    #1e293b    /* Elevated surface */
--steel-700:    #334155    /* Border, subtle */
--steel-500:    #64748b    /* Muted text */
--steel-300:    #cbd5e1    /* Secondary text */
--steel-100:    #f1f5f9    /* Primary text */
--accent-500:   #f97316    /* Safety orange - CTA */
--accent-400:   #fb923c    /* Orange hover */
--accent-600:   #ea580c    /* Orange pressed */
--warm-500:     #eab308    /* Welding spark gold */
```

#### Blue Steel Palette
- Source: https://www.schemecolor.com/blue-steel-color-scheme.php
```
Forest Blue:    #2A6A9E
Steel Blue:     #4682B4
Lake Blue:      #5E99C5
Light Blue:     #B6D4E7
Pale Silver:    #EBEBEB
Dark Silver:    #B0B0B0
```

#### Industrial Expertise Palette
- Source: https://www.schemecolor.com/industrial-expertise.php
- Tones: Deep charcoal, slate, rust, steel gray, safety yellow

#### Made of Steel (Canva)
- Source: https://www.canva.com/colors/color-palettes/made-of-steel/
- Theme: Neutral dark with metallic accents

### Recommended Color System for Cheolmoksu
```css
:root {
  /* Background layers (dark to light) */
  --bg-primary:     #0a0f1a;
  --bg-secondary:   #111827;
  --bg-elevated:    #1e293b;
  --bg-surface:     #1e293b;

  /* Text hierarchy */
  --text-primary:   #f1f5f9;
  --text-secondary: #94a3b8;
  --text-muted:     #64748b;

  /* Accent (Safety Orange - construction authority) */
  --accent:         #f97316;
  --accent-hover:   #fb923c;
  --accent-pressed: #ea580c;

  /* Semantic */
  --border:         #334155;
  --ring:           #f9731633;

  /* Special */
  --spark:          #fbbf24;  /* Welding spark gold */
  --steel-blue:     #4682B4;  /* Trust, structural */
}
```

---

## 8. SVG Illustrations

### General Purpose

#### unDraw
- **URL**: https://undraw.co/illustrations
- **License**: MIT-like (free for commercial use, no attribution required)
- **Format**: SVG (customizable colors)
- **Features**: Change primary color to match brand
- **Search**: "building", "construction", "house", "engineering", "design"
- **Best for**: About section, process explanations, empty states

#### Storyset (by Freepik)
- **URL**: https://storyset.com/
- **License**: Free with attribution, Premium without
- **Format**: SVG, customizable colors, animatable
- **Styles**: 4-5 illustration styles (minimal, trendy)
- **Features**: Built-in animation editor, Figma plugin
- **Best for**: Animated process steps, feature explanations

### Construction-Specific

#### IconScout Construction Illustrations
- **URL**: https://iconscout.com/illustrations/construction
- **License**: Free tier (limited) + Premium
- **Count**: 15,136 construction illustrations
- **Format**: SVG, PNG, EPS, AI
- **Best for**: Construction worker scenes, building process, tools

#### IconScout Building Illustrations
- **URL**: https://iconscout.com/illustrations/building
- **License**: Free tier + Premium
- **Count**: 29,796 building illustrations
- **Best for**: Building/house illustrations, architecture scenes

#### Vecteezy Construction SVGs
- **URL**: https://www.vecteezy.com/free-svg/construction
- **License**: Free with attribution (Vecteezy License)
- **Count**: 122,447 construction SVGs
- **Best for**: Large variety of construction-themed vector art

### Silhouettes & Minimal

#### SVG Silh
- **URL**: https://svgsilh.com/tag/construction-1.html
- **License**: CC0 Public Domain
- **Count**: 256 construction silhouette images
- **Format**: SVG
- **Best for**: Minimal decorative elements, loading states

#### Reshot Construction Icons
- **URL**: https://www.reshot.com/free-svg-icons/construction/
- **License**: Free for commercial use
- **Format**: SVG
- **Best for**: Alternative icon-style illustrations

### People Illustrations

#### Humaaans
- **URL**: https://www.humaaans.com/
- **License**: CC0 Public Domain (completely free)
- **Format**: SVG, Figma
- **Features**: Mix-and-match characters (poses, outfits, hairstyles)
- **Best for**: Team section, about page, testimonial avatars

### Recommended Illustration Strategy
1. **Hero section**: No illustrations (use real photos with overlay)
2. **Process/How-it-works**: Storyset animated SVGs (color-matched to brand)
3. **Feature cards**: Lucide/Phosphor icons (not illustrations)
4. **About/Team**: Humaaans or real team photos
5. **Empty states/Loading**: unDraw with steel-blue accent
6. **Decorative**: SVG Silh construction silhouettes at low opacity

---

## 9. Recommended Asset Combinations

### Minimal Stack (Pure HTML + Tailwind CDN)
Best for: Single-page landing page, fast build, maximum performance

| Category | Choice | CDN/Source |
|----------|--------|------------|
| Icons | Lucide | unpkg CDN |
| Photos | Unsplash + Pexels | Direct download, self-hosted |
| Patterns | Pure CSS (MagicPattern) | Inline CSS |
| Animations | AOS + CSS native | jsDelivr CDN |
| Components | Raw Tailwind | Tailwind CDN |
| Fonts | Pretendard + Noto Serif KR | jsDelivr + Google Fonts |
| Colors | Custom steel palette | CSS custom properties |
| Illustrations | unDraw + Lucide icons | Self-hosted SVG |

### Premium Stack (React/Next.js)
Best for: Interactive experience, maximum animation control

| Category | Choice | Install |
|----------|--------|---------|
| Icons | Lucide React + Phosphor Duotone | npm |
| Photos | Unsplash API | API integration |
| Patterns | Pure CSS + SVG noise | Inline |
| Animations | GSAP + Lenis + Motion | npm |
| Components | Tailwind + shadcn/ui | npm |
| Fonts | Pretendard + Noto Serif KR + Playfair | next/font |
| Colors | Custom Tailwind theme | tailwind.config |
| Illustrations | Storyset (animated) | Self-hosted SVG |

### Performance Budget
- Total font load: < 200KB (subset Korean characters)
- Icon bundle: < 15KB (tree-shake unused)
- Animation JS: < 50KB (GSAP core + ScrollTrigger)
- Images: WebP format, lazy-loaded, < 100KB per hero image
- Total page weight target: < 800KB first load

---

## 10. Licensing Summary

| Resource | License | Attribution | Commercial |
|----------|---------|------------|------------|
| Lucide | ISC | Not required | Yes |
| Heroicons | MIT | Not required | Yes |
| Phosphor | MIT | Not required | Yes |
| Unsplash | Unsplash License | Not required | Yes |
| Pexels | Pexels License | Not required | Yes |
| Pixabay | Pixabay License | Not required | Yes |
| Pretendard | SIL OFL | Not required | Yes |
| Noto Serif KR | SIL OFL | Not required | Yes |
| Playfair Display | SIL OFL | Not required | Yes |
| GSAP | Standard License | Not required | Yes (free) |
| AOS | MIT | Not required | Yes |
| Lenis | MIT | Not required | Yes |
| daisyUI | MIT | Not required | Yes |
| unDraw | MIT-like | Not required | Yes |
| Humaaans | CC0 | Not required | Yes |
| Freepik/Storyset | Freepik License | Required (free) | Yes |
| Vecteezy | Vecteezy License | Required (free) | Yes |
| IconScout | IconScout License | Varies | Free tier limited |

All primary recommended resources are fully free for commercial use with no attribution required.
