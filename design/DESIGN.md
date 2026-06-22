# Remember — Phase 2 Design Decisions
**Product:** Remember — $37 iOS 27 Siri Memory Setup System  
**Date:** June 22, 2026  
**Audience:** Women 30-44, moms, TikTok traffic  
**UX Lead directive:** Mobile-first, thumb-friendly, instant above-fold impact  
**UI Lead directive:** Warm, clean, trustworthy — mom-appropriate, not SaaS

---

## Color Palette

| Role | Color | Hex | Usage |
|---|---|---|---|
| **Background** | Warm cream/ivory | `#FAF8F4` | Page background |
| **Surface** | White | `#FFFFFF` | Cards, sections |
| **Accent / CTA** | Warm sage green | `#4A7C59` | Buttons, highlights |
| **Accent hover** | Deeper sage | `#3A6249` | Button hover state |
| **Headline text** | Deep charcoal | `#1A1A1A` | H1, H2 |
| **Body text** | Warm dark | `#3D3D3D` | Paragraphs, lists |
| **Subtle text** | Muted gray | `#8A8A8A` | Captions, footnotes |
| **Trust/badge** | Warm gold | `#C9A84C` | Star rating, badges |
| **Guarantee accent** | Soft terracotta | `#C96B4A` | Guarantee badge border |
| **Divider** | Light warm gray | `#EBEBEB` | Section separators |

**Rationale:** Warm neutrals signal warmth + trust. Sage green is the 2025-2026 "wellness-adjacent" color for women 30-44 — used by top-performing TikTok health/productivity brands (Seed, Hum, Cymbiotika). Deep charcoal over ivory = easy readability without harsh contrast. No navy, no cold blue.

---

## Typography

### Headline font
- **Playfair Display** — Google Fonts (serif)
- Weights used: 400 (regular), 700 (bold)
- Used for: H1, H2 section titles
- Character: Warm, trustworthy, premium without being corporate
- Load method: `<link rel="preconnect">` + subset to Latin

### Body font
- **Inter** — Google Fonts (sans-serif)
- Weights used: 400 (regular), 500 (medium), 600 (semibold)
- Used for: Body copy, CTAs, labels, captions
- Character: Clean, highly readable at small sizes, iOS-native feel

### Type scale (mobile-first)

| Element | Size (mobile) | Size (desktop) | Weight | Font |
|---|---|---|---|---|
| H1 (hero headline) | 32px / 2rem | 48px / 3rem | 700 | Playfair Display |
| H2 (section headline) | 26px / 1.625rem | 36px / 2.25rem | 700 | Playfair Display |
| H3 (sub-section) | 20px / 1.25rem | 24px / 1.5rem | 600 | Inter |
| Body | 17px / 1.0625rem | 18px / 1.125rem | 400 | Inter |
| CTA button text | 18px / 1.125rem | 18px / 1.125rem | 600 | Inter |
| Caption / footnote | 14px / 0.875rem | 14px / 0.875rem | 400 | Inter |

**Line height:** Body 1.65 (relaxed — mom readers appreciate breathing room)  
**Letter spacing:** Headlines -0.01em; Body 0; Buttons +0.02em (slightly wider for CTA readability)

---

## Spacing System (Mobile-First)

| Token | Value | Used for |
|---|---|---|
| `--space-xs` | 8px | Icon/badge margins |
| `--space-sm` | 16px | Text internal spacing |
| `--space-md` | 24px | Component internal padding |
| `--space-lg` | 40px | Section padding top/bottom (mobile) |
| `--space-xl` | 64px | Section padding top/bottom (desktop) |
| `--space-2xl` | 96px | Hero top padding |
| `--container-max` | 640px | Max content width (keeps everything thumb-scannable) |
| `--container-pad` | 20px | Page horizontal padding (mobile) |

**Rationale:** 40px section padding on mobile = generous, uncluttered. Max content width 640px ensures no content is ever in a far corner.

---

## Page Structure & Section Order

### Section 0: Sticky CTA Bar (persistent, bottom of screen)
- Always visible on mobile
- Contains: "Get Instant Access — $37" button
- Hides only while user is viewing above-fold CTA to prevent redundancy
- Background: Sage green (#4A7C59)
- Text: White, Inter 600

### Section 1: HERO (Above Fold)
- **Headline** (H1, Playfair Display): Match the TikTok ad hook — confusion/curiosity angle
- **Subhead** (Inter 400): One clarifying sentence about what this is
- **Trust bar**: ★★★★★ [PLACEHOLDER count] customers · 30-day guarantee
- **CTA button**: "Get Instant Access — $37" (full-width, sage green, 56px height)
- **Price context**: ~~$67~~ $37 today — or just "$37" with a note about what they get
- **No navigation menu** — none, ever
- No autoplay video (video placeholder — recommend same creator from TikTok ad)

Layout: Single column, centered, max 580px wide, heavy top padding (80px)

### Section 2: PROOF OF CONCEPT — "The Magic Demo"
- Show the exact Siri interaction (text-based, not video, as a visual call-out card)
- Screen mockup style: iPhone-frame visual showing the Q&A exchange
- Copy: Frame it as "What you'll be able to do in 15 minutes"
- No social proof yet — this is the curiosity payoff moment

### Section 3: PROBLEM / PAIN
- Section headline: Relatable pain statement
- 3-4 bullet pain points — short, real, specific
- Transition: "There's actually a way to fix all of this..."

### Section 4: HOW IT WORKS — 3 Steps
- Section headline: "Set it up in 15 minutes. Use it forever."
- 3 numbered steps with icons
- Step 1: Create your Remember list in Siri
- Step 2: Tell Siri what to remember (voice, hands-free)
- Step 3: Ask Siri anytime — instant recall
- Each step: icon + H3 title + 2-sentence description

### Section 5: WHAT'S INCLUDED
- Visual card-style list of everything in the $37 guide
- Clear, specific items (not vague "bonus content")
- Highlight: What you get vs. figuring it out yourself

### Section 6: SOCIAL PROOF — Testimonials
- 3 testimonial cards — [PLACEHOLDER names and quotes clearly marked]
- Format: Star rating + name + quote (1-2 sentences)
- Warm, specific, real-sounding placeholders
- "As Seen on TikTok" badge above this section

### Section 7: OFFER STACK
- Core product: $37
- **Order bump / upsell**: $17 Early Access / Beta Prep Pack (shown at checkout via Lemon Squeezy)
- On the page: Mention the upsell exists as a "add-on" — 1 paragraph below the CTA
- Note: The main upsell happens AT checkout, not on this page (Lemon Squeezy order bump)
- CTA: Same sage green button, full-width

### Section 8: GUARANTEE
- Prominent — not buried in footer
- 30-day money-back guarantee
- Warm, simple language — not legalistic
- Icon: Simple badge/shield graphic inline

### Section 9: FAQ
- 5 questions — top purchase objections
- Accordion style (collapsed by default, expand on tap)
- Clean dividers, Inter 400 body

### Section 10: FINAL CTA
- Repeat the headline (condensed version)
- Single CTA button
- Guarantee reminder (1 line)

### Footer
- Minimal: Company name, privacy policy link, contact email
- Copyright line
- No navigation, no social links, no distractions

---

## CTA Design Spec

- **Height:** 56px (mobile) — thumb-comfortable
- **Border radius:** 12px — friendly, modern, not harsh
- **Background:** Sage green `#4A7C59`
- **Hover:** `#3A6249` (slightly darker)
- **Active/press:** Scale 0.98 + darker shade
- **Text:** White, Inter 600, 18px, letter-spacing +0.02em
- **Shadow:** `0 4px 16px rgba(74,124,89,0.25)` — subtle green glow
- **Width:** Full-width on mobile (100%), max 420px on desktop
- **Transition:** 0.15s ease on all properties

---

## Mobile-First Layout Rules

1. **Single column always** — no two-column layouts at any breakpoint below 768px
2. **Tap targets minimum 48×48px** on all interactive elements
3. **No horizontal scroll** — all content within viewport
4. **Font sizes never below 16px** for body copy (prevents iOS zoom-on-tap)
5. **Images:** WebP format, max 480px wide on mobile, lazy-loaded except hero
6. **Sticky CTA bar:** `position: fixed; bottom: 0; left: 0; right: 0; z-index: 100`
7. **Padding:** 20px horizontal on mobile, 40px on tablet+
8. **No pop-ups or interstitials** that interrupt the scroll

---

## Offer Stack Display Design

### On-page mention (Section 7):
- Headline: "Want to go further?" or similar
- 1 paragraph describing the $17 Early Access / Beta Prep Pack
- Explained as an add-on at checkout, not a separate product
- No separate CTA — the main CTA button covers it ("it'll show up at checkout")

### At Checkout (Lemon Squeezy order bump):
- Handled by LS native order bump feature
- Appears as a checkbox on the checkout page: "Add: iOS 27 Early Access / Beta Prep Pack — $17"
- Short description: "How to get beta access, compatibility check, backup guide, and safe testing steps"

---

## Performance Budget (Sub-1.5s Target)

| Asset | Budget |
|---|---|
| HTML | < 20KB gzipped |
| CSS | < 15KB gzipped |
| JavaScript | < 10KB gzipped (FAQ accordion only) |
| Google Fonts | Load with `display=swap`, preconnect |
| Images | < 100KB total (WebP, lazy loaded) |
| Total page weight | < 250KB |
| Target LCP | < 1.2s |
| Target FID | < 50ms |
| Target CLS | < 0.05 |

---

## Visual Feel Reference

**Not:** SaaS dark mode, harsh contrast, startup-coded, blue-heavy, corporate grid  
**Yes:** Clean-girl journal aesthetic, slightly warm, white space, feels personal and made-for-you, like a really useful thing a smart friend built and is sharing

**Comparison brands (aesthetic reference only):** Goop (warmth without the woo), Notion's personal use marketing (clean, functional), Cal Newport content design (warm text-first)

---

*Design decisions complete. Phase 3 (Copy) is next.*
