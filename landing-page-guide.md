# 🚀 The Ultimate Landing Page Guide
### Every Detail You Need to Build a High-Converting, Beautiful Landing Page

---

## Table of Contents
1. [What Is a Landing Page?](#what-is-a-landing-page)
2. [Core Anatomy of a Landing Page](#core-anatomy)
3. [Design Principles](#design-principles)
4. [Typography](#typography)
5. [Color System](#color-system)
6. [Spacing & Layout](#spacing--layout)
7. [Hero Section — Full Breakdown](#hero-section)
8. [Navigation Bar](#navigation-bar)
9. [Social Proof Section](#social-proof-section)
10. [Features / Benefits Section](#features--benefits-section)
11. [Pricing Section](#pricing-section)
12. [FAQ Section](#faq-section)
13. [Footer](#footer)
14. [Call-to-Action (CTA) — The Most Critical Element](#call-to-action-cta)
15. [Animations & Micro-interactions](#animations--micro-interactions)
16. [Responsiveness](#responsiveness)
17. [Performance Optimization](#performance-optimization)
18. [Full HTML/CSS/JS Boilerplate](#full-boilerplate)

---

## 1. What Is a Landing Page?

A landing page is a **standalone web page** with a single, focused goal: to convert a visitor into a lead or customer. Unlike a homepage — which has many destinations — a landing page has **one action**, one message, one purpose.

### Types of Landing Pages
| Type | Goal | Example |
|---|---|---|
| Lead Generation | Collect emails | "Get the free eBook" |
| Sales | Sell a product | SaaS subscription page |
| Click-through | Warm up visitors | Pre-checkout page |
| Coming Soon | Build hype | Product launch waitlist |
| Webinar | Event registration | "Join the live class" |

---

## 2. Core Anatomy

Every high-converting landing page follows this structure:

```
┌─────────────────────────────────────┐
│           NAVIGATION BAR            │  ← minimal, no distractions
├─────────────────────────────────────┤
│                                     │
│             HERO SECTION            │  ← headline, subheadline, CTA
│                                     │
├─────────────────────────────────────┤
│         SOCIAL PROOF / LOGOS        │  ← trust signals
├─────────────────────────────────────┤
│       PROBLEM → SOLUTION BRIDGE     │  ← empathy + positioning
├─────────────────────────────────────┤
│         FEATURES / BENEFITS         │  ← what they get
├─────────────────────────────────────┤
│           TESTIMONIALS              │  ← real people, real results
├─────────────────────────────────────┤
│             PRICING                 │  ← clear, honest tiers
├─────────────────────────────────────┤
│               FAQ                   │  ← handle objections
├─────────────────────────────────────┤
│         FINAL CTA SECTION           │  ← last push to convert
├─────────────────────────────────────┤
│              FOOTER                 │  ← legal, links, socials
└─────────────────────────────────────┘
```

---

## 3. Design Principles

### The 5 Laws of Great Landing Page Design

**Law 1 — One Page, One Goal**
Remove every element that doesn't support the conversion goal. No blog links, no unrelated navigation.

**Law 2 — Above the Fold is Gold**
The first screen (without scrolling) must instantly communicate:
- What it is
- Who it's for
- What they should do next

**Law 3 — Visual Hierarchy**
Guide the eye using size, weight, contrast, and whitespace. The CTA should visually "pop" above everything else.

**Law 4 — Consistency**
Every color, font size, and component should follow the design system. Inconsistency breaks trust.

**Law 5 — Speed = Conversions**
Every 1-second delay in load time reduces conversions by ~7%. Optimize aggressively.

---

## 4. Typography

### Choosing Fonts
Pick **2 fonts maximum**: a display font for headings and a body font for paragraphs.

```css
/* Example: Elegant SaaS combination */
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');

:root {
  --font-display: 'Syne', sans-serif;   /* Headlines */
  --font-body:    'DM Sans', sans-serif; /* Body text */
}
```

### Type Scale (use this exact scale)

| Role | Size | Weight | Line Height |
|---|---|---|---|
| Hero Headline | 72px / 4.5rem | 800 | 1.05 |
| Section Headline | 48px / 3rem | 700 | 1.1 |
| Sub-headline | 28px / 1.75rem | 500 | 1.3 |
| Body text | 18px / 1.125rem | 400 | 1.7 |
| Small / Caption | 14px / 0.875rem | 400 | 1.5 |
| Button label | 16px / 1rem | 600 | 1 |

### Typography Rules
- **Max line length**: 65–75 characters (readable measure)
- **Hero text**: Tight leading (1.0–1.1) for punch
- **Body text**: Generous leading (1.6–1.8) for readability
- **Never**: use more than 3 font weights on one page

```css
/* Responsive font sizing using clamp() */
h1 {
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  line-height: 1.05;
  letter-spacing: -0.03em; /* Tighten large headings */
}

p {
  font-size: clamp(1rem, 1.5vw, 1.125rem);
  line-height: 1.7;
  max-width: 65ch; /* Limit line length */
}
```

---

## 5. Color System

### Building a Landing Page Color Palette

You need exactly **5 color roles**:

```css
:root {
  /* 1. Background — the canvas */
  --color-bg:         #0A0A0F;

  /* 2. Surface — cards, panels */
  --color-surface:    #13131A;

  /* 3. Border — subtle separators */
  --color-border:     #2A2A3A;

  /* 4. Text — primary & muted */
  --color-text:       #F0F0FF;
  --color-text-muted: #8888AA;

  /* 5. Accent — CTA, highlights */
  --color-accent:     #6C5CE7;
  --color-accent-glow: rgba(108, 92, 231, 0.4);
}
```

### Color Rules
- **60% — Background**: Dominant neutral
- **30% — Surface + text**: Secondary elements
- **10% — Accent**: CTA buttons, highlights, icons only
- Never use more than **1 accent color** (use shades of it instead)
- Always check **contrast ratio**: body text ≥ 4.5:1, large text ≥ 3:1

### Gradient Techniques
```css
/* Mesh gradient background */
.hero {
  background:
    radial-gradient(ellipse at 20% 50%, rgba(108,92,231,0.15) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 20%, rgba(0,206,201,0.10) 0%, transparent 60%),
    var(--color-bg);
}

/* Text gradient */
.gradient-text {
  background: linear-gradient(135deg, #6C5CE7, #00CEC9);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## 6. Spacing & Layout

### The 8px Grid System
Every spacing value should be a **multiple of 8px**:

```css
:root {
  --space-1:  8px;   /* Tight: icon gaps, inline spacing */
  --space-2:  16px;  /* Default: small padding */
  --space-3:  24px;  /* Medium: card padding */
  --space-4:  32px;  /* Section elements gap */
  --space-6:  48px;  /* Large gaps */
  --space-8:  64px;  /* Section padding */
  --space-12: 96px;  /* Between major sections */
  --space-16: 128px; /* Hero vertical padding */
}
```

### Container & Max-widths
```css
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-4);
}

/* Narrower for text-heavy content */
.container--text {
  max-width: 760px;
}
```

### CSS Grid Layouts

```css
/* Features: 3-column grid */
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-4);
}

/* 2-column hero: text + image */
.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-8);
  align-items: center;
}

@media (max-width: 768px) {
  .hero-grid { grid-template-columns: 1fr; }
}
```

---

## 7. Hero Section

The most critical section. You have **3–5 seconds** to hook the visitor.

### Hero Checklist
- [ ] **Headline**: Clear, benefit-focused, < 10 words
- [ ] **Sub-headline**: Expands on the headline, 1–2 sentences
- [ ] **Primary CTA button**: Action verb + value ("Start Free Trial")
- [ ] **Secondary CTA**: Lower commitment ("Watch Demo")
- [ ] **Social proof line**: "Trusted by 10,000+ teams"
- [ ] **Hero visual**: Product screenshot, illustration, or mockup

### Hero HTML Structure
```html
<section class="hero">
  <div class="container">
    <div class="hero-grid">

      <!-- Left: Copy -->
      <div class="hero-copy">

        <!-- Badge / Announcement -->
        <div class="hero-badge">
          <span class="badge-dot"></span>
          New: AI-powered analytics →
        </div>

        <!-- Main Headline -->
        <h1 class="hero-headline">
          Ship products that
          <span class="gradient-text">users love.</span>
        </h1>

        <!-- Sub-headline -->
        <p class="hero-sub">
          The all-in-one platform for product teams to collect feedback,
          prioritize features, and measure impact — in one beautiful workspace.
        </p>

        <!-- CTA Group -->
        <div class="cta-group">
          <a href="#signup" class="btn btn--primary">
            Start for free
            <svg><!-- arrow icon --></svg>
          </a>
          <a href="#demo" class="btn btn--ghost">
            <svg><!-- play icon --></svg>
            Watch 2-min demo
          </a>
        </div>

        <!-- Social Proof Line -->
        <div class="hero-social-proof">
          <div class="avatar-stack">
            <img src="avatar1.jpg" alt="">
            <img src="avatar2.jpg" alt="">
            <img src="avatar3.jpg" alt="">
          </div>
          <p>Loved by <strong>12,000+</strong> product teams worldwide</p>
        </div>

      </div>

      <!-- Right: Visual -->
      <div class="hero-visual">
        <img src="product-mockup.png" alt="Product dashboard" class="hero-image">
      </div>

    </div>
  </div>
</section>
```

### Hero CSS
```css
.hero {
  padding: var(--space-16) 0;
  position: relative;
  overflow: hidden;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-1);
  padding: 6px 14px;
  background: rgba(108,92,231,0.12);
  border: 1px solid rgba(108,92,231,0.3);
  border-radius: 100px;
  font-size: 0.875rem;
  color: var(--color-accent);
  margin-bottom: var(--space-3);
}

.badge-dot {
  width: 6px; height: 6px;
  background: var(--color-accent);
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.hero-headline {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 5.5vw, 4.5rem);
  font-weight: 800;
  line-height: 1.05;
  letter-spacing: -0.03em;
  margin-bottom: var(--space-3);
}

.hero-sub {
  font-size: 1.2rem;
  line-height: 1.7;
  color: var(--color-text-muted);
  max-width: 52ch;
  margin-bottom: var(--space-4);
}

.cta-group {
  display: flex;
  align-items: center;
  gap: var(--space-2);
  flex-wrap: wrap;
  margin-bottom: var(--space-4);
}

.hero-social-proof {
  display: flex;
  align-items: center;
  gap: var(--space-2);
  font-size: 0.9rem;
  color: var(--color-text-muted);
}

.avatar-stack {
  display: flex;
}

.avatar-stack img {
  width: 32px; height: 32px;
  border-radius: 50%;
  border: 2px solid var(--color-bg);
  margin-left: -8px;
}

.avatar-stack img:first-child { margin-left: 0; }

/* Hero image with glow */
.hero-image {
  width: 100%;
  border-radius: 16px;
  border: 1px solid var(--color-border);
  box-shadow:
    0 0 0 1px var(--color-border),
    0 40px 80px rgba(0,0,0,0.5),
    0 0 120px var(--color-accent-glow);
}
```

---

## 8. Navigation Bar

### Nav Rules
- Keep it **minimal** — logo + max 4 links + CTA
- Make it **sticky** with a blur backdrop
- CTA button should be **accent colored**
- On mobile: collapse to a hamburger menu

```html
<nav class="navbar">
  <div class="container nav-container">
    <a href="/" class="nav-logo">
      <img src="logo.svg" alt="Brand Logo">
    </a>

    <ul class="nav-links">
      <li><a href="#features">Features</a></li>
      <li><a href="#pricing">Pricing</a></li>
      <li><a href="#testimonials">Reviews</a></li>
    </ul>

    <div class="nav-cta">
      <a href="#login" class="btn btn--ghost btn--sm">Log in</a>
      <a href="#signup" class="btn btn--primary btn--sm">Get started</a>
    </div>
  </div>
</nav>
```

```css
.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  padding: var(--space-2) 0;
  background: rgba(10,10,15,0.8);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--color-border);
}

.nav-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: var(--space-4);
  margin: 0; padding: 0;
}

.nav-links a {
  color: var(--color-text-muted);
  text-decoration: none;
  font-size: 0.95rem;
  transition: color 0.2s;
}

.nav-links a:hover { color: var(--color-text); }
```

---

## 9. Social Proof Section

This section **builds trust** immediately. Place it just below the hero.

### Types of Social Proof
1. **Logo strip** — "As seen in" or "Trusted by" partner logos
2. **Star ratings** — G2, Capterra, Product Hunt scores
3. **User count** — "10,000+ companies"
4. **Testimonial cards** — Full quotes with photo & title
5. **Case study stats** — "2x faster, 40% cost reduction"

```html
<!-- Logo Strip -->
<section class="logos-section">
  <p class="logos-label">Trusted by teams at</p>
  <div class="logos-row">
    <img src="logo-stripe.svg" alt="Stripe">
    <img src="logo-notion.svg" alt="Notion">
    <img src="logo-vercel.svg" alt="Vercel">
    <img src="logo-figma.svg" alt="Figma">
    <img src="logo-linear.svg" alt="Linear">
  </div>
</section>
```

```css
.logos-section {
  padding: var(--space-8) 0;
  text-align: center;
  border-top: 1px solid var(--color-border);
  border-bottom: 1px solid var(--color-border);
}

.logos-label {
  color: var(--color-text-muted);
  font-size: 0.85rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: var(--space-3);
}

.logos-row {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-8);
  flex-wrap: wrap;
}

.logos-row img {
  height: 28px;
  opacity: 0.4;
  filter: grayscale(1);
  transition: opacity 0.3s;
}

.logos-row img:hover {
  opacity: 0.8;
  filter: grayscale(0);
}
```

---

## 10. Features / Benefits Section

### Features vs Benefits — Know the Difference
| Feature (What it does) | Benefit (What it means for you) |
|---|---|
| "Real-time sync" | "Never lose work again" |
| "AI-powered summaries" | "Save 3 hours per week" |
| "Role-based permissions" | "Keep your team organized" |

**Always lead with benefits, support with features.**

### Feature Card Component
```html
<section class="features" id="features">
  <div class="container">
    <div class="section-header">
      <h2>Everything you need.<br>Nothing you don't.</h2>
      <p>Built for modern product teams who move fast.</p>
    </div>

    <div class="features-grid">

      <!-- Feature Card -->
      <div class="feature-card">
        <div class="feature-icon">
          <svg><!-- Icon SVG --></svg>
        </div>
        <h3 class="feature-title">AI-Powered Insights</h3>
        <p class="feature-desc">
          Automatically surface patterns across thousands of user responses
          so you focus on decisions, not data wrangling.
        </p>
      </div>

      <!-- Repeat for other features -->
    </div>
  </div>
</section>
```

```css
.feature-card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: 16px;
  padding: var(--space-4);
  transition: border-color 0.3s, transform 0.3s;
}

.feature-card:hover {
  border-color: var(--color-accent);
  transform: translateY(-4px);
}

.feature-icon {
  width: 48px; height: 48px;
  background: rgba(108,92,231,0.15);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: var(--space-3);
  color: var(--color-accent);
}

.feature-title {
  font-size: 1.15rem;
  font-weight: 600;
  margin-bottom: var(--space-1);
}

.feature-desc {
  font-size: 0.95rem;
  color: var(--color-text-muted);
  line-height: 1.65;
}
```

---

## 11. Pricing Section

### Pricing Rules
- Always show **3 tiers** (Starter / Pro / Enterprise)
- Highlight the **recommended** plan visually
- Show **monthly / annual toggle** (annual = savings)
- List what's **included AND what's NOT** per tier
- CTA on each card

```html
<section class="pricing" id="pricing">
  <div class="container">
    <div class="section-header">
      <h2>Simple, honest pricing</h2>
      <!-- Toggle -->
      <div class="billing-toggle">
        <span>Monthly</span>
        <label class="toggle-switch">
          <input type="checkbox" id="billing-toggle">
          <span class="toggle-slider"></span>
        </label>
        <span>Annual <span class="save-badge">Save 20%</span></span>
      </div>
    </div>

    <div class="pricing-grid">

      <!-- Starter -->
      <div class="pricing-card">
        <div class="plan-name">Starter</div>
        <div class="plan-price"><span class="price-amount">$0</span>/mo</div>
        <p class="plan-desc">Perfect to get started.</p>
        <a href="#" class="btn btn--outline btn--full">Get started free</a>
        <ul class="plan-features">
          <li class="included">Up to 3 projects</li>
          <li class="included">Basic analytics</li>
          <li class="included">1 team member</li>
          <li class="excluded">AI insights</li>
          <li class="excluded">Priority support</li>
        </ul>
      </div>

      <!-- Pro — Featured -->
      <div class="pricing-card pricing-card--featured">
        <div class="plan-badge">Most Popular</div>
        <div class="plan-name">Pro</div>
        <div class="plan-price"><span class="price-amount">$49</span>/mo</div>
        <p class="plan-desc">For growing teams.</p>
        <a href="#" class="btn btn--primary btn--full">Start free trial</a>
        <ul class="plan-features">
          <li class="included">Unlimited projects</li>
          <li class="included">Advanced analytics</li>
          <li class="included">Up to 10 members</li>
          <li class="included">AI insights</li>
          <li class="excluded">Dedicated support</li>
        </ul>
      </div>

      <!-- Enterprise -->
      <div class="pricing-card">
        <div class="plan-name">Enterprise</div>
        <div class="plan-price"><span class="price-amount">Custom</span></div>
        <p class="plan-desc">For large organizations.</p>
        <a href="#" class="btn btn--outline btn--full">Talk to sales</a>
        <ul class="plan-features">
          <li class="included">Everything in Pro</li>
          <li class="included">Unlimited members</li>
          <li class="included">SSO / SAML</li>
          <li class="included">AI insights</li>
          <li class="included">Dedicated support</li>
        </ul>
      </div>

    </div>
  </div>
</section>
```

```css
.pricing-card--featured {
  border-color: var(--color-accent);
  background: linear-gradient(
    135deg,
    rgba(108,92,231,0.1),
    var(--color-surface)
  );
  position: relative;
  transform: scale(1.03);
}

.plan-features li {
  padding: 8px 0;
  font-size: 0.95rem;
  display: flex;
  gap: 10px;
  color: var(--color-text-muted);
}

.plan-features li.included { color: var(--color-text); }
.plan-features li.included::before { content: "✓"; color: #00b894; }
.plan-features li.excluded::before { content: "×"; color: var(--color-border); }
```

---

## 12. FAQ Section

Handle objections before they become reasons to leave.

```html
<section class="faq" id="faq">
  <div class="container container--text">
    <h2 class="section-title">Frequently asked questions</h2>

    <div class="faq-list">
      <details class="faq-item">
        <summary class="faq-question">
          Is there a free trial?
          <svg class="faq-chevron"><!-- chevron --></svg>
        </summary>
        <p class="faq-answer">
          Yes! Every paid plan starts with a 14-day free trial. No credit card required.
        </p>
      </details>

      <!-- Repeat for other questions -->
    </div>
  </div>
</section>
```

```css
.faq-item {
  border-bottom: 1px solid var(--color-border);
  padding: var(--space-3) 0;
}

.faq-question {
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  font-weight: 500;
  font-size: 1.05rem;
  list-style: none; /* Remove default triangle */
}

.faq-answer {
  color: var(--color-text-muted);
  padding-top: var(--space-2);
  line-height: 1.7;
  font-size: 0.95rem;
}

details[open] .faq-chevron {
  transform: rotate(180deg);
}

.faq-chevron {
  transition: transform 0.3s ease;
  flex-shrink: 0;
}
```

---

## 13. Footer

```html
<footer class="footer">
  <div class="container">
    <div class="footer-grid">

      <div class="footer-brand">
        <img src="logo.svg" alt="Logo" class="footer-logo">
        <p>The platform for modern product teams.</p>
        <div class="social-links">
          <a href="#" aria-label="Twitter"><!-- Twitter SVG --></a>
          <a href="#" aria-label="GitHub"><!-- GitHub SVG --></a>
          <a href="#" aria-label="LinkedIn"><!-- LinkedIn SVG --></a>
        </div>
      </div>

      <div class="footer-links">
        <h4>Product</h4>
        <ul>
          <li><a href="#">Features</a></li>
          <li><a href="#">Pricing</a></li>
          <li><a href="#">Changelog</a></li>
          <li><a href="#">Roadmap</a></li>
        </ul>
      </div>

      <div class="footer-links">
        <h4>Company</h4>
        <ul>
          <li><a href="#">About</a></li>
          <li><a href="#">Blog</a></li>
          <li><a href="#">Careers</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>

      <div class="footer-links">
        <h4>Legal</h4>
        <ul>
          <li><a href="#">Privacy Policy</a></li>
          <li><a href="#">Terms of Service</a></li>
          <li><a href="#">Cookie Policy</a></li>
        </ul>
      </div>

    </div>

    <div class="footer-bottom">
      <p>© 2026 YourBrand Inc. All rights reserved.</p>
    </div>
  </div>
</footer>
```

---

## 14. Call-to-Action (CTA) — The Most Critical Element

### CTA Button Design
```css
/* Primary button */
.btn--primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 28px;
  background: var(--color-accent);
  color: #fff;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  position: relative;
  overflow: hidden;
}

.btn--primary::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(to bottom, rgba(255,255,255,0.1), transparent);
}

.btn--primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px var(--color-accent-glow);
}

.btn--primary:active {
  transform: translateY(0);
}

/* Ghost / Outline button */
.btn--ghost {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 28px;
  background: transparent;
  color: var(--color-text);
  border: 1px solid var(--color-border);
  border-radius: 10px;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
}

.btn--ghost:hover {
  border-color: var(--color-text-muted);
  background: rgba(255,255,255,0.03);
}
```

### CTA Copywriting Rules
| ❌ Weak | ✅ Strong |
|---|---|
| Submit | Get instant access |
| Click here | Start building free |
| Sign up | Join 12,000+ teams |
| Download | Get my free guide |
| Buy | Start my trial |

---

## 15. Animations & Micro-interactions

```css
/* Fade-in on scroll */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-on-scroll {
  opacity: 0;
  animation: fadeInUp 0.6s ease forwards;
}

/* Pulse animation for badge dot */
@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50%       { opacity: 0.5; transform: scale(0.85); }
}

/* Shimmer loading state */
@keyframes shimmer {
  0%   { background-position: -1000px 0; }
  100% { background-position: 1000px 0; }
}
```

```javascript
// Intersection Observer for scroll animations
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      entry.target.style.animationDelay = `${i * 0.1}s`;
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.animate-on-scroll').forEach(el => {
  observer.observe(el);
});
```

---

## 16. Responsiveness

### Breakpoints
```css
/* Mobile first approach */
:root {
  --bp-sm: 480px;
  --bp-md: 768px;
  --bp-lg: 1024px;
  --bp-xl: 1280px;
}

/* Usage */
@media (max-width: 768px) {
  .hero-grid { grid-template-columns: 1fr; }
  .nav-links { display: none; } /* → hamburger menu */
  .features-grid { grid-template-columns: 1fr; }
  .pricing-grid { grid-template-columns: 1fr; }
  .pricing-card--featured { transform: none; }
  .cta-group { flex-direction: column; align-items: stretch; }
}
```

### Mobile Nav (Hamburger)
```javascript
const hamburger = document.querySelector('.hamburger');
const navLinks = document.querySelector('.nav-links');

hamburger.addEventListener('click', () => {
  navLinks.classList.toggle('nav-open');
  hamburger.setAttribute('aria-expanded',
    navLinks.classList.contains('nav-open')
  );
});
```

---

## 17. Performance Optimization

### Checklist
- [ ] Use **WebP** images with `<picture>` fallback
- [ ] Set explicit `width` and `height` on images (prevents layout shift)
- [ ] Lazy load below-the-fold images: `loading="lazy"`
- [ ] Use `font-display: swap` for web fonts
- [ ] Minify CSS/JS before shipping
- [ ] Use a CDN for static assets
- [ ] Add `<link rel="preconnect">` for Google Fonts
- [ ] Enable gzip / brotli compression on server

```html
<!-- Preload critical font -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<!-- Preload hero image -->
<link rel="preload" as="image" href="hero-mockup.webp">

<!-- Lazy load below-fold images -->
<img src="feature.webp" loading="lazy" width="600" height="400" alt="Feature">
```

```html
<!-- Responsive images with WebP -->
<picture>
  <source srcset="hero.webp" type="image/webp">
  <img src="hero.png" alt="Hero" width="800" height="600">
</picture>
```

---

## 18. Full HTML Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>YourBrand — Tagline here</title>

  <!-- SEO -->
  <meta name="description" content="One-sentence description of your product, max 155 chars.">
  <meta name="robots" content="index, follow">

  <!-- Open Graph (social sharing) -->
  <meta property="og:title" content="YourBrand — Tagline">
  <meta property="og:description" content="One-sentence description.">
  <meta property="og:image" content="https://yourdomain.com/og-image.png">
  <meta property="og:url" content="https://yourdomain.com">
  <meta property="og:type" content="website">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="YourBrand — Tagline">
  <meta name="twitter:description" content="One-sentence description.">
  <meta name="twitter:image" content="https://yourdomain.com/og-image.png">

  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="/favicon.svg">

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

  <!-- CSS -->
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- Navigation -->
  <nav class="navbar">...</nav>

  <!-- Hero -->
  <section class="hero" id="home">...</section>

  <!-- Logo Strip -->
  <section class="logos-section">...</section>

  <!-- Features -->
  <section class="features" id="features">...</section>

  <!-- Testimonials -->
  <section class="testimonials" id="testimonials">...</section>

  <!-- Pricing -->
  <section class="pricing" id="pricing">...</section>

  <!-- FAQ -->
  <section class="faq" id="faq">...</section>

  <!-- Final CTA -->
  <section class="cta-section">
    <div class="container">
      <h2>Ready to get started?</h2>
      <p>Join 12,000+ teams already using YourBrand.</p>
      <a href="#signup" class="btn btn--primary btn--lg">Start for free →</a>
    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">...</footer>

  <!-- JS -->
  <script src="main.js" defer></script>

</body>
</html>
```

---

## Quick Reference Card

```
FONTS:        Display + Body, max 2 families, max 3 weights
TYPE SCALE:   72 / 48 / 28 / 18 / 14px
COLORS:       Bg / Surface / Border / Text / Accent (60/30/10 rule)
SPACING:      8px grid — 8, 16, 24, 32, 48, 64, 96, 128px
CONTAINER:    max-width: 1200px, padding: 0 32px
BREAKPOINT:   Mobile ≤ 768px
SECTIONS:     Nav → Hero → Logos → Features → Testimonials
              → Pricing → FAQ → Final CTA → Footer
CTA COPY:     Action verb + clear value, no passive language
PERFORMANCE:  WebP, lazy load, preconnect, font-display: swap
```

---

*Built with intention. Designed with precision. Converted with purpose.*
