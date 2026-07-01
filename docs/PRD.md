# PRD: Comprehensive PRD, Website Audit & Clone Implementation Plan for B2Broker Website

**Document Version:** 1.0
**Date:** July 2, 2026
**Prepared by:** Petra, AI Product Manager — AI Employee OS
**Website Under Analysis:** https://b2broker.com/
**Status:** Ready for Engineering Review

---

## 1. Executive Summary

### 1.1 About B2Broker

B2Broker is a leading B2B technology and liquidity provider for the financial services industry. The company provides turnkey solutions for Forex, crypto, and CFD brokerages, including liquidity aggregation, trading platform white-labels (MT5, cTrader), CRM systems, payment processing (B2BinPay), back-office platforms, and investment platform solutions. The website serves as a comprehensive marketing, lead generation, and educational hub targeting institutional clients, brokerage startups, and fintech companies globally.

### 1.2 Project Scope

This PRD defines the full specification for building a production-ready clone of the B2Broker website. The clone will replicate the site's information architecture, marketing workflows, content management capabilities, multi-language support, SEO structure, lead generation funnels, and UI/UX experience. The project targets functional parity with the existing site while using a modern, maintainable tech stack.

### 1.3 Key Characteristics of the Source Site

- **Multi-language support:** English, German, French, Spanish, Farsi, Arabic, Hindi, Russian, Chinese, and more (10+ locales based on sitemap analysis with `/de/`, `/fr/`, `/es/`, `/fa/`, `/ar/`, `/hi/`, `/ru/` prefixes).
- **Content volume:** Hundreds of blog/news articles, dozens of product pages, event pages, author profile pages, case studies, and resource pages.
- **Dynamic modules:** Blog CMS, product catalog, event listings, lead-gen forms, newsletter subscription, demo request workflows, downloadable resources, video integrations.
- **B2B focus:** Conversion funnels designed for enterprise lead capture, not e-commerce transactions.
- **Sitemap structure:** Segmented XML sitemaps (blog-articles, blog-events, blog-authors, etc.), indicating a mature, SEO-optimized content architecture.

### 1.4 Business Objectives for the Clone

1. Achieve visual and functional parity with b2broker.com.
2. Provide a fully manageable CMS for all content types.
3. Support 10+ languages with locale-based URL routing.
4. Deliver sub-3-second page load times globally.
5. Enable lead capture and CRM integration workflows.
6. Ensure scalability for 500+ content pages and 50K+ monthly visitors.

---

## 2. Tech Stack Recommendation

### 2.1 Frontend

| Layer | Technology | Justification |
|---|---|---|
| Framework | **Next.js 14+ (App Router)** | Server-side rendering for SEO, built-in i18n routing (`/de/`, `/fr/`), image optimization, static generation for content-heavy pages, React ecosystem. |
| Language | **TypeScript** | Type safety across a large codebase with many content models. |
| Styling | **Tailwind CSS + custom design tokens** | Rapid UI development, responsive utilities, easy theming to match B2Broker's design system. |
| Animation | **Framer Motion** | Scroll-triggered animations, slider transitions, hero effects observed on the source site. |
| State Management | **React Context + Zustand** | Lightweight global state for language selector, form state, navigation state. |
| Forms | **React Hook Form + Zod** | Performant form handling with schema validation for lead-gen forms. |

### 2.2 Backend

| Layer | Technology | Justification |
|---|---|---|
| CMS | **Strapi v5 (Headless CMS)** | Open-source, supports i18n natively, REST + GraphQL APIs, role-based access, media library, customizable content types for products/blogs/events/authors. |
| API Layer | **Next.js API Routes + Strapi API** | Next.js handles BFF (backend-for-frontend) concerns like form submission proxying; Strapi handles content CRUD. |
| Runtime | **Node.js 20 LTS** | Unified JS/TS runtime across frontend and backend. |
| Email Service | **SendGrid or AWS SES** | Transactional emails for form confirmations, newsletter, and internal lead notifications. |
| Search | **Meilisearch** | Fast, typo-tolerant full-text search for blog articles, products, and resources. Self-hosted, lightweight. |

### 2.3 Database & Storage

| Layer | Technology | Justification |
|---|---|---|
| Database | **PostgreSQL 16** | Robust relational DB, native JSON support, excellent Strapi compatibility, handles multi-locale content well. |
| Media Storage | **AWS S3 / Cloudflare R2** | Scalable object storage for images, PDFs, videos, downloadable resources. |
| CDN | **Cloudflare** | Global edge caching, DDoS protection, image resizing, fast TTFB worldwide. |

### 2.4 Infrastructure & DevOps

| Layer | Technology | Justification |
|---|---|---|
| Hosting | **AWS (ECS Fargate) or Vercel (frontend) + AWS (Strapi)** | Vercel for Next.js optimizes SSR/SSG; Strapi on containerized AWS for CMS stability. |
| CI/CD | **GitHub Actions** | Automated linting, testing, build, preview deployments, production releases. |
| Monitoring | **Sentry (errors) + Datadog or Grafana (infra)** | Error tracking, performance monitoring, uptime alerts. |
| Analytics | **Google Analytics 4 + Google Tag Manager** | Marketing analytics, conversion tracking, event tracking. |
| Security | **Helmet.js, rate limiting, CSRF tokens, WAF (Cloudflare)** | Standard web security hardening. |

---

## 3. Site Structure & Pages

### 3.1 Complete Sitemap

Based on the website analysis, the B2Broker site contains the following page categories and representative pages. Each page is replicated per supported locale (10+ languages), meaning the total localized page count is approximately 10× the base English count.

#### 3.1.1 Core / Static Pages

| # | URL Path | Purpose | Key Components | Content Type |
|---|---|---|---|---|
| 1 | `/` | Homepage / hero landing | Hero slider, product overview cards, partner logos, stats counters, testimonials, CTA sections, news ticker, video embed | Dynamic (CMS-managed hero, stats, testimonials) |
| 2 | `/about` | Company overview | Company history timeline, leadership team, mission/values, office locations, partner logos | Semi-static |
| 3 | `/contact` | Contact page | Contact form, office addresses with maps, phone/email details, department selector | Static + form |
| 4 | `/careers` | Careers / jobs | Open positions listing, culture section, benefits, application form | Dynamic |
| 5 | `/partners` | Partnership program | Partner tiers, benefits, registration form, existing partner logos | Semi-static |
| 6 | `/sitemap` | HTML sitemap | Auto-generated link tree of all pages | Dynamic |

#### 3.1.2 Product Pages (Dynamic — CMS-managed)

| # | URL Path Pattern | Purpose | Key Components | Content Type |
|---|---|---|---|---|
| 7 | `/liquidity` | Forex & crypto liquidity | Product hero, feature grids, pricing tiers, asset class lists, integration diagram, CTA | Dynamic |
| 8 | `/trading-platform` | MT5/cTrader white-label | Platform comparison, feature tables, screenshots, demo request form | Dynamic |
| 9 | `/crypto-payment-gateway` | B2BinPay payment processing | Integration flow, supported coins, API docs link, pricing | Dynamic |
| 10 | `/crm` | B2Core CRM platform | Feature breakdown, screenshots, module list, demo CTA | Dynamic |
| 11 | `/investment-platform` | PAMM/MAM/Copy trading | Product features, investor/manager flows, diagrams | Dynamic |
| 12 | `/back-office` | Back-office solution | Admin features, compliance tools, reporting | Dynamic |
| 13 | `/white-label-solutions` | Turnkey brokerage packages | Package comparison, included components, pricing CTA | Dynamic |
| 14 | `/b2binpay` | Crypto payment details | Detailed B2BinPay product page | Dynamic |
| 15 | `/turnkey-brokerage` | Full brokerage setup | End-to-end setup flow, what's included, timeline | Dynamic |

#### 3.1.3 Blog / News / Articles (Dynamic — CMS-managed)

| # | URL Path Pattern | Purpose | Key Components | Content Type |
|---|---|---|---|---|
| 16 | `/news` | Blog listing / news hub | Category filters, paginated article cards, featured article, search | Dynamic |
| 17 | `/news/[slug]` | Individual article | Article body (rich text), author bio, related articles, social share, TOC, reading time | Dynamic |
| 18 | `/author/[slug]` | Author profile | Author bio, photo, list of authored articles | Dynamic |

Based on sitemap data, there are **200+ unique articles** (e.g., `a-book-vs-b-book-brokers`, `mt5-white-label-compliance`, `mt5-white-label-cost`, `why-brokers-lose-clients`, `importance-of-crm-customization`, `add-ctrader-alongside-mt5`, `how-to-scale-a-forex-brokerage`, `multi-asset-support-across-multi-markets`, etc.).

#### 3.1.4 Events Pages (Dynamic — CMS-managed)

| # | URL Path Pattern | Purpose | Key Components | Content Type |
|---|---|---|---|---|
| 19 | `/news/[event-slug]` (event category) | Event announcement/recap | Event details, location, date, photo gallery, recap content | Dynamic |

Example events from sitemap: `b2broker-and-b2binpay-to-lead-the-way-in-blockchain-innovation-at-paris-blockchain-week`, `b2binpay-eqwire-at-pay360-conference-report`, `getting-ready-for-crypto-talks-on-the-token-2049-singapore-expo`, `ready-to-shine-at-the-finance-magnates-pacific-summit-expo-2024`.

#### 3.1.5 Resource / Legal Pages

| # | URL Path Pattern | Purpose | Key Components | Content Type |
|---|---|---|---|---|
| 20 | `/resources` | Downloadable resources hub | Filterable resource cards, gated download forms | Dynamic |
| 21 | `/glossary` or `/wiki` | Financial glossary | Alphabetical term listing, search, individual term pages | Dynamic |
| 22 | `/privacy-policy` | Privacy policy | Legal text | Static |
| 23 | `/terms-of-service` | Terms of service | Legal text | Static |
| 24 | `/cookie-policy` | Cookie policy | Legal text | Static |
| 25 | `/aml-policy` | AML/KYC policy | Legal text | Static |

### 3.2 Page Count Summary

| Category | Base Pages (EN) | Localized Total (est. 10 locales) |
|---|---|---|
| Core / Static | 6 | 60 |
| Product Pages | 9 | 90 |
| Blog Articles | 200+ | 2,000+ |
| Event Pages | 30+ | 300+ |
| Author Pages | 10+ | 100+ |
| Resource/Legal | 6 | 60 |
| **Total** | **~260+** | **~2,600+** |

---

## 4. Frontend Components Inventory

### 4.1 Global / Layout Components

| Component | Description | Variants |
|---|---|---|
| `GlobalHeader` | Sticky top navigation bar with logo, mega-menu, language selector, CTA button ("Talk to Sales") | Desktop, mobile hamburger |
| `MegaMenu` | Multi-column dropdown menus for Products, Solutions, Company sections | Per-category columns with icons, descriptions, links |
| `MobileDrawer` | Full-screen slide-out navigation for mobile | Accordion sub-menus |
| `LanguageSelector` | Dropdown/modal for switching locale | 10+ language flags/labels |
| `GlobalFooter` | Multi-column footer with link groups, social icons, newsletter signup, legal links, certifications | Standard, minimal |
| `CookieConsent` | GDPR cookie consent banner | Banner, preferences modal |
| `Breadcrumbs` | Hierarchical breadcrumb navigation | Standard |
| `BackToTop` | Floating scroll-to-top button | Appears on scroll |

### 4.2 Hero / Landing Components

| Component | Description |
|---|---|
| `HeroSlider` | Full-width hero with rotating slides (image/video backgrounds, headline, subheadline, CTA buttons) |
| `HeroBanner` | Static hero with background image, title, description, and CTA for interior pages |
| `VideoHero` | Hero section with embedded/background video |
| `StatsCounter` | Animated number counters (e.g., "700+ institutional clients", "$5B daily volume") |
| `TrustBar` | Horizontal row of partner/client logos |

### 4.3 Content Components

| Component | Description |
|---|---|
| `RichTextRenderer` | Renders CMS rich-text/markdown content with embedded images, tables, code blocks |
| `FeatureGrid` | 2–4 column grid of feature cards with icons and descriptions |
| `FeatureSection` | Alternating image-left/text-right (and vice versa) feature blocks |
| `ComparisonTable` | Side-by-side product/plan comparison table |
| `AccordionFAQ` | Expandable FAQ sections |
| `TabsPanel` | Tabbed content sections (e.g., product feature tabs) |
| `TimelineComponent` | Vertical or horizontal timeline (company history, setup process) |
| `TestimonialCarousel` | Client testimonials with avatar, name, company, quote |
| `PricingCard` | Pricing tier cards with feature lists and CTA |
| `IconCard` | Small card with icon, title, and short description |
| `DiagramViewer` | Architecture/flow diagrams (may use SVG or embedded images) |

### 4.4 Blog / News Components

| Component | Description |
|---|---|
| `ArticleCard` | Card with thumbnail, title, excerpt, author, date, category tag |
| `ArticleListPage` | Paginated grid of `ArticleCard` with category filters and search |
| `ArticleDetail` | Full article layout: TOC sidebar, rich text body, author bio card, related articles |
| `AuthorCard` | Author avatar, name, bio snippet, link to author page |
| `CategoryFilter` | Horizontal pill/tag filter for blog categories |
| `SocialShareBar` | Share buttons (LinkedIn, Twitter/X, Facebook, email, copy link) |
| `ReadingProgressBar` | Top-of-page progress indicator showing scroll position |
| `TableOfContents` | Auto-generated sticky TOC from article headings |

### 4.5 Form Components

| Component | Description |
|---|---|
| `ContactForm` | Multi-field form: name, email, company, phone, country, message, subject/department |
| `DemoRequestForm` | Product-specific demo request (product selector, company size, timeline) |
| `NewsletterSignup` | Email-only inline form in footer or sidebar |
| `ResourceDownloadForm` | Gated form: name, email, company → unlocks PDF download |
| `PartnerApplicationForm` | Extended form for partnership inquiries |
| `FormField` | Reusable input, textarea, select, phone-with-country-code, checkbox components |
| `FormSuccessModal` | Confirmation modal/message after form submission |

### 4.6 Interactive / Media Components

| Component | Description |
|---|---|
| `ImageSlider` | Multi-image carousel with navigation arrows and dots |
| `VideoEmbed` | YouTube/Vimeo embed with lazy loading and poster image |
| `LightboxGallery` | Click-to-expand image gallery (event photos, screenshots) |
| `AnimatedOnScroll` | Wrapper for scroll-triggered fade/slide animations |
| `InteractiveMap` | Office locations map (Google Maps or Mapbox embed) |
| `SearchOverlay` | Full-screen search modal with instant results |

### 4.7 SEO / Utility Components

| Component | Description |
|---|---|
| `SEOHead` | Dynamic `<head>` with title, meta description, OG tags, hreflang tags, canonical URL |
| `SchemaMarkup` | JSON-LD structured data (Organization, Article, BreadcrumbList, FAQPage, Product) |
| `HreflangTags` | Alternate language link tags for all supported locales |
| `SitemapGenerator` | XML sitemap generation (segmented like source: articles, events, authors) |

---

## 5. Backend & API Requirements

### 5.1 Authentication & Authorization

| Requirement | Details |
|---|---|
| Admin authentication | JWT-based login for Strapi CMS admin panel; support for email/password and optional SSO |
| Role-based access | Roles: Super Admin, Content Editor, Translator, Marketing Manager, Developer |
| API authentication | API tokens for frontend-to-CMS communication; public read-only endpoints for published content; authenticated endpoints for draft/preview |
| No end-user auth | The public website has no user accounts or login; all auth is admin-side only |

### 5.2 API Endpoints (Strapi Content API)

All endpoints support locale filtering (`?locale=en`, `?locale=de`, etc.) and pagination.

#### Content Resources (CRUD via Strapi)

| Resource | Endpoints | Key Fields |
|---|---|---|
| **Pages** | `GET /api/pages`, `GET /api/pages/:slug` | title, slug, body (rich text), seo_meta, locale, template, components (dynamic zones) |
| **Products** | `GET /api/products`, `GET /api/products/:slug` | name