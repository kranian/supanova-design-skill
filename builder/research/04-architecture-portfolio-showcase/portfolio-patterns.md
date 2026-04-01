# Architecture/Construction Portfolio Showcase Design Patterns

Research for "Cheolmoksu" (철목수) landing page portfolio section design.
Covers steel house construction projects, custom steel fabrication, and YouTube process documentation.

---

## 1. Before/After Project Galleries

### Why It Works

Before/after comparisons are the single most persuasive visual pattern for construction portfolios. They provide immediate, tangible proof of transformation capability. Potential clients can envision what is possible for their own projects.

### Image Comparison Slider Pattern

The interactive before/after slider lets users drag a divider across overlapping images to reveal the transformation.

**Technical Implementation:**
- HTML: Two images stacked in a container with a draggable divider element
- CSS: `overflow: hidden` on the container; the "before" image clips via `clip-path` or container width
- JS: Pointer/touch event listeners update the clip position on drag
- Always include touch support for mobile (pointer events, not just mouse events)
- Reference: [W3Schools Image Comparison Tutorial](https://www.w3schools.com/howto/howto_js_image_comparison.asp)
- Reference: [DEV Community - Creating an Image Comparison Slider](https://dev.to/mursalfk/creating-an-image-comparison-slider-with-html-css-and-javascript-5dmn)

**Layout Recommendation for Cheolmoksu:**
```
+--------------------------------------------------+
|  [Before/After Slider - Full Width Hero Image]    |
|  <--- drag handle --->                            |
|  Label: "시공 전" / "시공 후"                       |
+--------------------------------------------------+
|  Project Title  |  Location  |  Duration  |  Type |
+--------------------------------------------------+
```

### Static Before/After Grid

For pages listing multiple projects, a side-by-side static grid is simpler and loads faster:

```
+---------------------+  +---------------------+
|  Before (muted)     |  |  After (vibrant)    |
|  [grayscale filter]  |  |  [full color]       |
+---------------------+  +---------------------+
   Project Name - Location - Year
```

**Design Tips:**
- Apply a subtle grayscale or desaturation filter to "before" images to create visual contrast
- Use consistent image aspect ratios (16:9 for exteriors, 4:3 for interiors)
- Minimum image resolution: 1200px wide for retina displays
- Add a hover/tap interaction to toggle between before and after states

---

## 2. Construction Process Timeline Presentations

### Vertical Timeline Pattern

Best for mobile-first design. Each phase is a node on a vertical line with alternating left/right content blocks.

```
    [Icon] Phase 1: Design & Planning (설계)
    |
    |--- Photo + Description
    |
    [Icon] Phase 2: Foundation & Steel Frame (기초/철골)
    |
    |--- Photo + Description
    |
    [Icon] Phase 3: Exterior Finish (외장)
    |
    |--- Photo + Description
    |
    [Icon] Phase 4: Interior & Completion (내장/완공)
         |
         --- Photo + Description
```

**Recommended Phases for Steel House Construction:**
1. Consultation & Site Survey (상담/현장조사)
2. Design & Blueprint (설계/도면)
3. Steel Frame Fabrication (철골 제작)
4. Foundation Work (기초 공사)
5. Steel Frame Erection (철골 조립)
6. Exterior/Roofing (외장/지붕)
7. Interior Finish (내장 마감)
8. Final Inspection & Handover (최종 검수/인도)

### Horizontal Timeline Pattern

Works well for desktop. Each phase is a step on a horizontal track with progress indicators.

```
[1]----[2]----[3]----[4]----[5]----[6]----[7]----[8]
 ▼      ▼      ▼      ▼      ▼      ▼      ▼      ▼
상담   설계   제작   기초   조립   외장   내장   완공
```

**Design Tips:**
- Use scroll-triggered animations: each phase fades/slides in as user scrolls
- Include a progress bar or step indicator showing completion percentage
- Add duration labels (e.g., "2 weeks", "3 weeks") between phases
- Link each phase to the corresponding YouTube video for detailed documentation
- On mobile, collapse to an accordion or vertical layout
- Reference: [Venngage Timeline Examples](https://venngage.com/blog/timeline-examples/)

### Photo Journal Timeline

A chronological photo stream showing the actual construction progress over time:

```
+-------+  +-------+  +-------+  +-------+
| Day 1 |  | Week 2|  | Week 4|  | Week 8|
| Photo |  | Photo |  | Photo |  | Photo |
+-------+  +-------+  +-------+  +-------+
  Caption    Caption    Caption    Caption
```

This format works especially well for Cheolmoksu since they already document their process on YouTube.

---

## 3. Video Integration Patterns (YouTube Embed Best Practices)

### Performance Problem

A single YouTube iframe embed adds 1.3-2.6 MB to page weight and can increase load time by up to 2 seconds. A page with 5 YouTube videos can waste 10+ MB of initial bandwidth.

- Reference: [Why YouTube Embeds Hurt Your Website](https://swarmify.com/blog/why-youtube-embeds-hurt-your-website/)
- Reference: [CSS-Tricks - Lazy Load YouTube](https://css-tricks.com/lazy-load-embedded-youtube-videos/)

### Recommended: Facade/Lite Embed Pattern

Load only a thumbnail image and play button initially. The actual YouTube player loads only when the user clicks play.

**Implementation Options:**

1. **lite-youtube-embed (Recommended)**
   - Custom web component by Paul Irish (Google Chrome team)
   - 224x faster than stock iframe on heavy pages
   - GitHub: `paulirish/lite-youtube-embed`
   - Usage: `<lite-youtube videoid="VIDEO_ID"></lite-youtube>`

2. **srcdoc Approach**
   - Use iframe `srcdoc` attribute with a minimal HTML page containing just the thumbnail
   - On click, replace srcdoc with actual YouTube embed URL
   - No external dependency needed

3. **Native Lazy Loading (Minimum)**
   - Add `loading="lazy"` to iframe elements
   - Browser skips loading until the iframe scrolls into viewport
   - Least effort but least performance gain

### YouTube Embed Parameters for Portfolio Sites

```
?rel=0              // Disable related videos from other channels
&modestbranding=1   // Remove YouTube logo
&autoplay=1         // Auto-play after facade click
&playsinline=1      // Prevent fullscreen on iOS
```

### Layout Patterns for Video Integration

**Pattern A: Video Hero with Project Details**
```
+--------------------------------------------------+
|  [YouTube Video - 16:9 Facade]                    |
|  ▶ Play Button Overlay                           |
+--------------------------------------------------+
|  Project Title        |  Duration: 12 weeks       |
|  Location: Yangpyeong |  Type: Steel Frame House  |
+--------------------------------------------------+
```

**Pattern B: Video Gallery Grid**
```
+----------------+  +----------------+  +----------------+
| [▶ Thumbnail]  |  | [▶ Thumbnail]  |  | [▶ Thumbnail]  |
| 철골 제작 과정  |  | 기초 공사       |  | 조립 현장       |
+----------------+  +----------------+  +----------------+
```

**Pattern C: Inline Process Video within Timeline**
Each timeline phase includes an optional embedded video alongside photos and text. Video plays in-place when clicked, without navigating away.

### Privacy & SEO Notes

- Use `youtube-nocookie.com` domain for GDPR-friendly embeds
- Add structured data (VideoObject schema) for SEO
- Provide a text transcript or summary below each video for accessibility and SEO
- Reference: [SennaLabs - Embed YouTube Without Slowing Down](https://sennalabs.com/blog/how-to-embed-youtube-without-slowing-down-your-website)

---

## 4. Project Case Study Page Layouts

### Recommended Page Structure

Based on analysis of top architecture and construction portfolio sites:

```
Section 1: Hero Image (full-bleed project photo)
Section 2: Project Overview (title, location, type, year, area)
Section 3: Challenge & Solution narrative
Section 4: Before/After comparison
Section 5: Process timeline or photo journal
Section 6: Video walkthrough (YouTube embed)
Section 7: Technical specifications
Section 8: Client testimonial
Section 9: Related projects CTA
```

### Three Portfolio Types for Construction Companies

Based on [MayeCreate's analysis](https://mayecreate.com/blog/construction-portfolio-examples-what-type-should-your-construction-company-use/):

| Type | Best For | Pros | Cons |
|------|----------|------|------|
| **Photo Gallery** | Residential builders, remodelers | Immediate visual impact, simple to maintain | Low SEO value, no narrative |
| **Project Overview** | Engineering firms, service-focused | Good SEO, shows capability range | De-emphasizes photography |
| **Hybrid Gallery + Overview** | Architects, commercial builders | Best of both worlds, strong SEO | Higher development cost |

**Recommendation for Cheolmoksu:** The **Hybrid** approach is ideal. Steel house construction is visually impressive (great photos), but the custom fabrication process also needs explanation (technical narrative).

### Case Study Content Framework

For each project, include:

1. **Project Metadata** (at a glance)
   - Project name
   - Location (지역)
   - Building type (주택/상업/기타)
   - Total area (연면적)
   - Construction period (시공 기간)
   - Steel frame type (철골 구조 유형)

2. **Narrative** (600 words maximum)
   - Client's requirements and vision
   - Site-specific challenges
   - Design and engineering solutions
   - Construction highlights
   - Final outcome

3. **Visual Evidence**
   - 8-15 curated photos per project
   - At least one before/after pair
   - One process video (YouTube)
   - Floor plan or blueprint (if applicable)

- Reference: [Pixpa - How to Make an Architecture Portfolio](https://www.pixpa.com/blog/how-to-make-an-architecture-portfolio)
- Reference: [UXPin - UX Case Study Guide](https://www.uxpin.com/studio/blog/ux-case-study/)

---

## 5. Image Gallery Grid Systems and Lightbox Patterns

### Grid Layout Options

**A. Uniform Grid (Recommended for Project Listing Pages)**
```
+--------+  +--------+  +--------+
| 16:9   |  | 16:9   |  | 16:9   |
| Photo  |  | Photo  |  | Photo  |
+--------+  +--------+  +--------+
| Title  |  | Title  |  | Title  |
| Type   |  | Type   |  | Type   |
+--------+  +--------+  +--------+
```
- 3 columns on desktop, 2 on tablet, 1 on mobile
- Consistent aspect ratios create visual order
- CSS: `display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 24px;`

**B. Masonry Grid (Best for Mixed-Aspect Photo Galleries)**
```
+--------+  +-------------+  +--------+
| Tall   |  | Wide        |  | Square |
| Photo  |  | Photo       |  | Photo  |
|        |  +-------------+  +--------+
|        |  +--------+       +--------+
+--------+  | Square |       | Tall   |
+--------+  | Photo  |       | Photo  |
| Wide   |  +--------+       |        |
| Photo  |                   |        |
+--------+                   +--------+
```
- CSS: `columns: 3; column-gap: 16px;` or CSS Grid with `grid-auto-flow: dense`
- Native CSS masonry is coming (`grid-template-rows: masonry`) but not yet widely supported
- For now, use CSS columns or a lightweight JS library
- Reference: [FreeFrontEnd - CSS Masonry Layouts](https://freefrontend.com/css-masonry-layouts/)

**C. Featured + Grid (Recommended for Project Detail Pages)**
```
+----------------------------------+
|  Featured Hero Image (full-width)|
+----------------------------------+
+--------+  +--------+  +--------+
| Detail |  | Detail |  | Detail |
+--------+  +--------+  +--------+
+--------+  +--------+  +--------+
| Detail |  | Detail |  | Detail |
+--------+  +--------+  +--------+
```

### Lightbox Implementation

**Recommended Pattern:**
- Click/tap on any grid image opens a full-screen overlay
- Dark backdrop (rgba(0,0,0,0.9)) to focus attention on the image
- Navigation: left/right arrows, swipe on mobile, keyboard arrows
- Close: X button, Escape key, click outside image
- Include caption with project name and image description
- Preload adjacent images for smooth navigation
- Disable body scroll when lightbox is open

**Technical Approach:**
- Use `<dialog>` element for native modal behavior and accessibility
- CSS: `backdrop-filter: blur(8px)` for modern frosted glass effect
- Lazy load gallery images; load full-resolution only when lightbox opens
- Touch gesture support: pinch-to-zoom, swipe to navigate
- Reference: [CodingNepal - Masonry Gallery with Lightbox](https://www.codingnepalweb.com/masonry-image-gallery-with-lightbox-html-css/)

### Image Optimization Guidelines

| Context | Max Width | Format | Quality |
|---------|-----------|--------|---------|
| Grid thumbnail | 640px | WebP with JPEG fallback | 80% |
| Lightbox full | 1920px | WebP with JPEG fallback | 85% |
| Hero/featured | 2560px | WebP with JPEG fallback | 85% |
| Before/after slider | 1200px | WebP with JPEG fallback | 85% |

---

## 6. Stats/Numbers Presentation

### Why Numbers Work

People trust numbers more than words. Animated counters create a "mini-celebration of success" that catches attention and makes accomplishments feel significant. For construction companies, stats serve as powerful trust signals.

- Reference: [Embeddable - Number Counter Widget](https://embeddable.co/blog/how-to-create-number-counter-for-your-website)
- Reference: [Landingfolio - Stats Section Examples](https://www.landingfolio.com/components/stats)

### Recommended Stats for Cheolmoksu

```
+------------+  +------------+  +------------+  +------------+
|   150+     |  |   20+      |  |   15+      |  |   98%      |
| 시공 실적   |  | 시공 경력   |  | 시공 유형   |  | 고객 만족   |
| Projects   |  | Years Exp. |  | Build Types|  | Satisfaction|
+------------+  +------------+  +------------+  +------------+
```

### Counter Animation Pattern

**Scroll-Triggered Count-Up:**
- Numbers start at 0 and animate to final value when section enters viewport
- Use Intersection Observer API to trigger animation
- Duration: 1.5-2.5 seconds per counter
- Easing: ease-out (fast start, slow finish) feels natural
- Add "+" suffix for approximate values

**Implementation Skeleton:**
```javascript
// Intersection Observer triggers count-up when stats section is visible
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      animateCounters(entry.target);
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.3 });
```

### Layout Recommendations

**Pattern A: Horizontal Bar (Recommended for Landing Page)**
- 4 stats in a row on desktop, 2x2 on mobile
- Large numbers (48-64px font size) with small labels below
- Background: dark or accent color to create visual separation
- Optional: subtle icon above each number

**Pattern B: Embedded in Hero Section**
- Stats overlaid on a construction photo
- Semi-transparent dark overlay behind numbers
- Creates immediate credibility above the fold

**Pattern C: Sidebar Stats**
- Vertical stack of stats alongside project narrative
- Works well in case study pages

---

## 7. Client Testimonial Integration with Project Showcases

### Strategic Placement

Testimonials should not be isolated in a separate section. The most effective approach ties each testimonial directly to a specific project.

- Reference: [Justinmind - 25 Testimonial Examples](https://www.justinmind.com/blog/testimonial-examples/)
- Reference: [Webflow Blog - Testimonials on Website](https://webflow.com/blog/testimonials-on-website)
- Reference: [LogRocket - Social Proof Examples](https://blog.logrocket.com/ux-design/19-social-proof-examples/)

### Testimonial Formats

**A. Project-Linked Testimonial Card**
```
+--------------------------------------------------+
|  [Project Photo]                                  |
|                                                   |
|  "철목수님 덕분에 꿈에 그리던 집을 지었습니다.       |
|   꼼꼼한 시공과 소통이 정말 좋았습니다."            |
|                                                   |
|  --- 김OO, 양평 철골주택 (2024)                    |
+--------------------------------------------------+
```

**B. Quote Carousel on Landing Page**
- Auto-rotating testimonials with client name and project reference
- Pause on hover/touch
- Manual navigation dots
- 5-7 second rotation interval
- Include client photo (with permission) for 35% higher trust

**C. Video Testimonial**
- Most powerful format for construction (clients can show their actual home)
- Use YouTube facade pattern (same as project videos)
- 60-90 second maximum for landing page embeds
- Add text quote as fallback/summary below the video

### Testimonial Content Guidelines

Effective construction testimonials should include:
- Specific mention of the project type
- Comment on the construction process (communication, timeline adherence)
- Comment on the final quality
- Quantifiable detail if possible (e.g., "3 months ahead of schedule")

### Integration with Before/After

Pair testimonials with before/after images for maximum impact:

```
+---------------------+  +---------------------+
|  Before             |  |  After              |
+---------------------+  +---------------------+
|  "처음 이 땅을 봤을 때는 막막했는데,              |
|   지금은 매일 집에 오는 게 행복합니다."           |
|   --- Client Name, Project Location            |
+--------------------------------------------------+
```

---

## Complete Landing Page Section Order Recommendation

For Cheolmoksu's landing page, the recommended section flow:

```
1. Hero Section
   - Full-bleed construction/completed project video or image
   - Headline: core value proposition
   - CTA: "시공 문의하기" / "포트폴리오 보기"

2. Stats Bar
   - 4 key numbers with scroll-triggered animation
   - Dark background for contrast

3. Featured Projects (Before/After)
   - 3-4 best projects with before/after slider
   - Each links to full case study page

4. Construction Process
   - Vertical timeline showing 6-8 phases
   - Each phase with photo and optional YouTube link

5. Video Showcase
   - 3-6 YouTube process videos in grid (facade pattern)
   - Categorized: design, fabrication, assembly, completion

6. Project Gallery
   - Filterable grid (by type: residential, commercial, custom)
   - Masonry or uniform grid
   - Lightbox on click

7. Testimonials
   - 3-5 client testimonials linked to specific projects
   - At least one video testimonial

8. CTA / Contact
   - Final conversion section
   - Phone, consultation form, location map
```

---

## Sources

### Architecture Portfolio Design
- [SiteBuilder Report - Architecture Portfolios: 30+ Examples](https://www.sitebuilderreport.com/inspiration/architect-websites)
- [Pravaah Consulting - 15 Best Architecture Websites 2026](https://www.pravaahconsulting.com/post/architecture-website-designs)
- [Pixpa - How to Make an Architecture Portfolio (14 Best Practices)](https://www.pixpa.com/blog/how-to-make-an-architecture-portfolio)
- [Pixpa - 14+ Architecture Portfolio Website Examples](https://www.pixpa.com/blog/architecture-portfolio-websites)
- [WebsitePlanet - 19 Best Architecture Portfolio Examples](https://www.websiteplanet.com/blog/best-architecture-portfolio-examples/)

### Construction Website Design
- [Pravaah Consulting - 15 Best Construction Website Designs 2026](https://www.pravaahconsulting.com/post/best-construction-company-websites)
- [MayeCreate - Construction Portfolio Types](https://mayecreate.com/blog/construction-portfolio-examples-what-type-should-your-construction-company-use/)
- [BuiltFor Studio - Project & Media Galleries for Construction](https://builtfor.studio/services/website-design-and-development/project-showcases-media-galleries/)
- [Projectmark - Construction Website Design Essential Elements](https://www.projectmark.com/blog/construction-website-design)
- [DigitalThrive - 25 Construction Company Design Examples](https://digitalthriveai.com/en-us/resources/how-to/web-design/25-construction-company-design-examples-we-love-how-to-make-your-own/)

### YouTube Embed Performance
- [Swarmify - Why YouTube Embeds Hurt Your Website (2026)](https://swarmify.com/blog/why-youtube-embeds-hurt-your-website/)
- [CSS-Tricks - Lazy Load Embedded YouTube Videos](https://css-tricks.com/lazy-load-embedded-youtube-videos/)
- [SennaLabs - Embed YouTube Without Slowing Down](https://sennalabs.com/blog/how-to-embed-youtube-without-slowing-down-your-website)
- [Clipara - Embed YouTube Without Slowing Pages](https://www.getclipara.com/guides/how-to-embed-youtube-videos-without-slowing-down-your-pages)
- [jQuery Script - 7 Best YouTube Lazy Loaders (2026)](https://www.jqueryscript.net/blog/best-youtube-video-lazy-load.html)

### Before/After Slider
- [W3Schools - How To Compare Two Images](https://www.w3schools.com/howto/howto_js_image_comparison.asp)
- [DEV Community - Creating an Image Comparison Slider](https://dev.to/mursalfk/creating-an-image-comparison-slider-with-html-css-and-javascript-5dmn)
- [DEV Community - Before and After Slider in Pure CSS](https://dev.to/rossangus/before-and-after-image-slider-in-pure-css-2oo3)
- [CodeMyUI - Before After Comparison Slider Designs](https://codemyui.com/tag/before-and-after/)

### Image Gallery & Grid Systems
- [FreeFrontEnd - 15 Pure CSS Masonry Layouts](https://freefrontend.com/css-masonry-layouts/)
- [CodingNepal - Masonry Gallery with Lightbox](https://www.codingnepalweb.com/masonry-image-gallery-with-lightbox-html-css/)
- [CSS Script - 10 Best Responsive Grid Layouts (2026)](https://www.cssscript.com/top-10-javascript-css-responsive-grid-layouts/)
- [FullStack Foundations - Next.js Masonry Gallery + Lightbox](https://www.fullstackfoundations.com/blog/nextjs-masonry-image-gallery-lightbox)

### Stats & Numbers
- [Embeddable - Number Counter Widget Guide](https://embeddable.co/blog/how-to-create-number-counter-for-your-website)
- [Landingfolio - 39+ Website Stats Examples](https://www.landingfolio.com/components/stats)
- [DesignModo - Infographics and Statistics in Web Design](https://designmodo.com/infographics-statistics-web-design/)

### Testimonials & Social Proof
- [Justinmind - 25 Testimonial Examples and Best Practices](https://www.justinmind.com/blog/testimonial-examples/)
- [Webflow Blog - 8 Examples of Testimonials on Website](https://webflow.com/blog/testimonials-on-website)
- [LogRocket - 19 Social Proof Examples for Designers](https://blog.logrocket.com/ux-design/19-social-proof-examples/)
- [Webstacks - 10 Best Customer Testimonials Page Designs](https://www.webstacks.com/blog/testimonial-page)
- [WPEngine - How to Feature Client Testimonials](https://wpengine.com/resources/client-testimonials/)

### Hero Section Design
- [Prismic - Website Hero Section Best Practices](https://prismic.io/blog/website-hero-section)
- [Magic UI - Hero Section Design Best Practices](https://magicui.design/blog/hero-section-design)
- [LogRocket - Hero Section Examples and Best Practices](https://blog.logrocket.com/ux-design/hero-section-examples-best-practices/)

### Case Study Structure
- [UXfol.io - Ultimate UX Case Study Template (2026)](https://blog.uxfol.io/ux-case-study-template/)
- [UXPin - UX Case Study Step-by-Step Guide](https://www.uxpin.com/studio/blog/ux-case-study/)
- [Webflow - Case Study Website Templates](https://webflow.com/templates/search/case-studies)

### Timeline Design
- [Venngage - 40+ Timeline Examples and Templates](https://venngage.com/blog/timeline-examples/)
