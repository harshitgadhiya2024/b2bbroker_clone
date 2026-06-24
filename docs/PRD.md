# PRD: Comprehensive PRD, Website Audit & Clone Implementation Plan for B2Broker Website

**Document Version:** 1.0
**Prepared by:** Petra – AI Product Manager, AI Employee OS
**Date:** June 25, 2026
**Status:** Draft for Engineering Review

---

## 1. Executive Summary

B2Broker (https://b2broker.com/) is a B2B financial technology company positioning itself as a **Prime of Prime Liquidity and Technology Provider** for brokers, banks, crypto exchanges, and payment providers. The website serves as the primary digital storefront and lead generation engine for a complex suite of financial infrastructure products including:

- Multi-asset liquidity provisioning
- Forex and Crypto broker turnkey solutions
- White-label trading platforms
- CRM and back-office systems
- Crypto payment gateways

**Clone Project Scope:**
This project aims to build a **production-ready functional clone** of the B2Broker website — replicating its architecture, UX/UI patterns, content management capabilities, dynamic features, SEO structure, and conversion funnels. The clone will serve as a white-label SaaS marketing site template for fintech companies offering similar B2B services.

**Key Facts:**
- ~25 sitemap pages identified; 8 deeply analyzed
- Primary stack: Next.js (React-based SSR/SSG), WebSocket for real-time data
- Heavy emphasis on lead generation (Book a Demo CTAs, email capture forms)
- Multi-product catalog with sub-navigation per product
- Content: blog, case studies, resources, regulatory/licensing info

---

## 2. Tech Stack Recommendation

### 2.1 Frontend

| Layer | Technology | Justification |
|---|---|---|
| Framework | **Next.js 14+ (App Router)** | Mirrors B2Broker's confirmed stack. Enables SSR, SSG, ISR for SEO-critical pages. |
| UI Library | **Tailwind CSS + shadcn/ui** | Rapid, consistent component building; utility-first matches complex fintech design systems. |
| Animation | **Framer Motion** | Handles the scroll-triggered animations, hero transitions, and counter animations seen on B2Broker. |
| State Management | **Zustand** | Lightweight, sufficient for UI state, modal management, and multi-step form flows. |
| Forms | **React Hook Form + Zod** | Robust validation for lead gen forms, inquiry flows, and newsletter signup. |
| Real-time | **WebSocket (native) / Socket.io** | Replicates live data (liquidity pricing, market specs) as confirmed in tech analysis. |
| i18n | **next-intl** | Multi-language support (B2Broker supports multiple languages). |

### 2.2 Backend

| Layer | Technology | Justification |
|---|---|---|
| Runtime | **Node.js + Express or Fastify** | Standard, scalable REST API layer compatible with Next.js API routes or standalone. |
| CMS | **Strapi v4 (headless CMS)** | Open-source, self-hostable, ideal for managing blog, products, case studies, and media. |
| Auth | **NextAuth.js / Auth.js** | Covers admin portal and potential gated resource downloads. |
| Email | **SendGrid** | Transactional emails (form confirmations, lead notifications). |
| CRM Bridge | **HubSpot API / Webhook forwarding** | Lead capture from forms → CRM pipeline (mirrors B2Broker's likely HubSpot/Salesforce setup). |

### 2.3 Database

| Layer | Technology | Justification |
|---|---|---|
| Primary DB | **PostgreSQL** | Relational, strong for structured content, lead records, user roles, product metadata. |
| ORM | **Prisma** | Type-safe, migration-friendly, integrates well with Next.js and Node. |
| Cache | **Redis** | Session caching, rate limiting on forms, real-time feed buffering. |
| Search | **Meilisearch** | Fast, typo-tolerant search across blog posts, products, and resources. |

### 2.4 Infrastructure & DevOps

| Layer | Technology | Justification |
|---|---|---|
| Hosting | **Vercel (frontend) + Railway or AWS ECS (backend/CMS)** | Vercel is purpose-built for Next.js; Railway for low-ops backend hosting. |
| CDN | **Cloudflare** | DDoS protection, edge caching, image optimization — critical for global fintech audiences. |
| Storage | **AWS S3 + CloudFront** | Media assets, downloadable resources (PDFs, whitepapers). |
| CI/CD | **GitHub Actions** | Automated testing, build, preview deployments, and production releases. |
| Monitoring | **Sentry + Datadog** | Error tracking and performance monitoring. |

### 2.5 Analytics & Marketing

| Tool | Purpose |
|---|---|
| Google Analytics 4 | Traffic, conversion tracking |
| Google Tag Manager | Tag management without deploys |
| Hotjar | Heatmaps, session recordings for UX optimization |
| HubSpot (free/starter) | CRM, lead nurturing, form integrations |

---

## 3. Site Structure & Pages

### 3.1 Complete Sitemap (25 Pages)

#### **Static / Marketing Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 1 | `/` | Homepage | Dynamic/Static Hybrid | Primary brand entry, lead gen | Hero section, product highlights, stats counter, testimonials, blog preview, email CTA |
| 2 | `/about/` | About Us | Static | Company overview, team, history | Timeline, team cards, mission statement, awards |
| 3 | `/contact/` | Contact | Dynamic | Lead capture, office locations | Contact form, map embed, office cards |
| 4 | `/careers/` | Careers | Dynamic | Job listings, employer branding | Job list (API-driven), culture section, apply modal |
| 5 | `/news/` | News & Press | Dynamic | Company announcements | News card grid, category filter, pagination |
| 6 | `/partners/` | Partners | Static | Partner ecosystem | Partner logo grid, partnership CTA |

#### **Product Pages (Turnkey Solutions)**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 7 | `/products/liquidity/` | Liquidity | Dynamic | Liquidity product detail | Asset class tabs, margin spec table, licensing cards, connectivity section, FAQ accordion |
| 8 | `/products/forex-broker-turnkey/` | Forex Broker Turnkey | Dynamic | Forex broker solution | Component breakdown, product stack cards, roadmap timeline, demo CTA |
| 9 | `/products/cryptocurrency-exchange-turnkey/` | Crypto Exchange Turnkey | Dynamic | Crypto exchange solution | Feature grid, mobile app section, testimonials, comparison table |
| 10 | `/products/crypto-broker-turnkey/` | Crypto Broker Turnkey | Dynamic | Crypto broker solution | B2TRADER breakdown, LP comparison, infrastructure diagram, FAQ |
| 11 | `/products/b2core/` | B2CORE CRM | Dynamic | CRM product detail | Feature list, screenshot gallery, integration map |
| 12 | `/products/b2trader/` | B2TRADER Platform | Dynamic | Trading platform detail | Platform features, asset support, tech specs |
| 13 | `/products/b2binpay/` | B2BinPay | Dynamic | Crypto payment gateway | Payment flow diagram, supported coins, integration guide |
| 14 | `/products/b2copy/` | B2COPY | Dynamic | Copy trading solution | Trader leaderboard (demo), performance stats, setup steps |
| 15 | `/products/mt-services/` | MT4/MT5 Services | Dynamic | MetaTrader services | Service tiers, pricing table, FAQ |

#### **White Label Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 16 | `/white-label/` | White Label Overview | Static | WL product hub | Product WL cards, CTA banner |
| 17 | `/white-label/ctrader/` | cTrader White Label | Dynamic | cTrader WL product | Feature comparison, licensing info, CTA |

#### **Blog / Content Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 18 | `/blog/` | Blog Index | Dynamic | Content marketing hub | Article grid, category filter, search bar, featured post |
| 19 | `/blog/[slug]/` | Blog Post | Dynamic | Individual article | Rich text content, author card, related posts, social share, newsletter CTA |

#### **Resource Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 20 | `/library/` | Resource Library | Dynamic | Whitepapers, guides, tools | Filterable resource grid, gated download modal |
| 21 | `/library/[slug]/` | Resource Detail | Dynamic | Individual resource | Download CTA, preview, related resources |

#### **Sector Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 22 | `/sectors/brokers/` | For Brokers | Static | Sector landing page | Use case narrative, product links, CTA |
| 23 | `/sectors/exchanges/` | For Exchanges | Static | Sector landing page | Use case narrative, product links, CTA |
| 24 | `/sectors/banks/` | For Banks | Static | Sector landing page | Use case narrative, product links, CTA |

#### **Legal Pages**

| # | URL Path | Page Name | Type | Purpose | Key Components |
|---|---|---|---|---|---|
| 25 | `/legal/privacy-policy/` | Privacy Policy | Static | Legal compliance | Long-form text, anchor navigation |
| 26 | `/legal/terms/` | Terms of Service | Static | Legal compliance | Long-form text |
| 27 | `/legal/aml-policy/` | AML Policy | Static | Regulatory compliance | Long-form text |

**Summary:**
- **Static Pages:** ~10
- **Dynamic Pages:** ~17
- **Total Pages (incl. dynamic routes):** ~27+ (scales with blog/resource content)

---

## 4. Frontend Components Inventory

### 4.1 Layout Components

| Component | Description |
|---|---|
| `<MainNav>` | Sticky top navigation with mega menus, logo, CTA button ("Contact us"), mobile hamburger |
| `<MegaMenu>` | Dropdown overlay for Products, Turnkey, WhiteLabel, Services, Sectors — with icon cards per item |
| `<SubNav>` | Product-specific sticky secondary nav (e.g., Overview / Components / FAQ / Book a Demo) |
| `<Footer>` | Multi-column footer with nav links, social icons, regulatory disclaimers, newsletter form |
| `<CookieBanner>` | GDPR cookie consent with accept/reject |

### 4.2 Hero & Section Components

| Component | Description |
|---|---|
| `<HeroSection>` | Full-width hero with headline, subtext, dual CTAs (Book a Demo / Try Demo), animated background |
| `<StatCounter>` | Animated number counters (e.g., "500+ customers", "10 asset classes") |
| `<TestimonialSlider>` | Auto-rotating client testimonial carousel with company logo and quote |
| `<LogoStrip>` | Horizontal scrolling strip of client/partner logos |
| `<VideoModal>` | Inline or popup video player (product demo videos) |
| `<ProductHighlightSection>` | Two-column layout: text left, screenshot/animation right |
| `<FeatureGrid>` | 3–4 column icon + text feature grid |
| `<ComparisonTable>` | Side-by-side product/tier comparison table |
| `<RoadmapTimeline>` | Horizontal or vertical product release roadmap |
| `<CTABanner>` | Full-width colored CTA section with headline and button |

### 4.3 Product-Specific Components

| Component | Description |
|---|---|
| `<AssetClassTabs>` | Tabbed interface for Forex / Crypto / CFD / Metals / etc. with specs per tab |
| `<MarginSpecTable>` | Data table: instrument, spread, margin requirement, leverage |
| `<LicenseCard>` | Card showing license type, jurisdiction, regulatory body |
| `<ConnectivityDiagram>` | Visual diagram of liquidity aggregation and distribution flow |
| `<ComponentStack>` | Visual breakdown of turnkey solution components (B2CORE + B2TRADER + etc.) |
| `<MobileAppSection>` | Phone mockup + feature highlights for mobile trading app |
| `<FAQAccordion>` | Expandable Q&A accordion (per-product FAQ) |
| `<PricingTierCard>` | Pricing plan card with feature list and CTA |

### 4.4 Blog & Content Components

| Component | Description |
|---|---|
| `<ArticleCard>` | Blog post preview: thumbnail, category tag, title, date, excerpt, read more link |
| `<ArticleGrid>` | Responsive 3-column grid of ArticleCards |
| `<CategoryFilter>` | Horizontal pill/tab filter for blog categories |
| `<SearchBar>` | Input with instant Meilisearch results dropdown |
| `<ArticleBody>` | Rich text renderer with heading anchors, inline images, code blocks |
| `<AuthorCard>` | Author avatar, name, bio, social links |
| `<RelatedPosts>` | 3-article horizontal row at end of blog post |
| `<ResourceCard>` | Downloadable resource card: icon, title, type badge, download CTA |
| `<GatedDownloadModal>` | Email capture modal triggered before resource download |

### 4.5 Form Components

| Component | Description |
|---|---|
| `<BookDemoForm>` | Multi-field lead form: name, email, company, product interest, phone, message |
| `<EmailCaptureBar>` | Inline single-field email form (homepage, footer) |
| `<NewsletterForm>` | Email + consent checkbox subscription form |
| `<ContactForm>` | Full contact form with department selector and file attachment |
| `<InquiryModal>` | Slide-in or modal form for product-specific inquiries |
| `<FormSuccessState>` | Confirmation view after form submission |

### 4.6 Utility Components

| Component | Description |
|---|---|
| `<LanguageSwitcher>` | Dropdown to switch between supported locales |
| `<Breadcrumb>` | SEO-friendly breadcrumb navigation on product/blog pages |
| `<SocialShareBar>` | LinkedIn, Twitter, Facebook, copy-link share buttons |
| `<ScrollProgressBar>` | Top-of-page reading progress indicator on blog posts |
| `<ToastNotification>` | Success/error toast after form submissions |
| `<Skeleton>` | Loading skeleton for dynamic content areas |
| `<Pagination>` | Page-based navigation for blog, news, resource listings |
| `<BackToTop>` | Fixed floating back-to-top button |

---

## 5. Backend & API Requirements

### 5.1 Authentication & Authorization

- **Admin CMS Auth:** Email + password login for Strapi CMS admin panel
- **Role-Based Access Control (RBAC):**
  - `super-admin`: Full access
  - `editor`: Create/edit blog, resources, products
  - `viewer`: Read-only dashboard access
- **API Key Auth:** For external integrations (HubSpot webhook, email service)
- **Rate Limiting:** On all public-facing form submission endpoints (Redis-backed, 5 submissions/IP/hour)

### 5.2 API Endpoints

#### Leads & Forms

```
POST   /api/leads/demo-request       — Book a Demo form submission
POST   /api/leads/contact            — Contact form submission
POST   /api/leads/newsletter         — Newsletter subscription
POST   /api/leads/resource-download  — Gated resource download capture
GET    /api/leads/[id]               — (Admin) Retrieve single lead
GET    /api/leads                    — (Admin) List all leads with filters
DELETE /api/leads/[id]               — (Admin) Delete lead record
```

#### Blog / Content (CMS-driven via Strapi REST or GraphQL)

```
GET    /api/posts                    — List blog posts (paginated, filterable by category/tag)
GET    /api/posts/[slug]             — Single blog post by slug
GET    /api/categories               — List all blog categories
GET    /api/tags                     — List all tags
POST   /api/posts                    — (Admin) Create post
PUT    /api/posts/[id]               — (Admin) Update post
DELETE /api/posts/[id]               — (Admin) Delete post
```

#### Products

```
GET    /api/products                 — List all products
GET    /api/products/[slug]          — Product detail with components, FAQ, specs
PUT    /api/products/[id]            — (Admin) Update product content
```

#### Resources / Library

```
GET    /api/resources                — List downloadable resources (type, category filter)
GET    /api/resources/[slug]         — Resource detail + secure download URL
POST   /api/resources/[slug]/access  — Email capture → return signed S3 URL
```

#### Search

```
GET    /api/search?q={query}         — Full-text search across posts, products, resources
```

#### Settings / Config

```
GET    /api/settings/navigation      — Dynamic nav structure for mega menu
GET    /api/settings/site            — Global site settings (logo, contact info, social links)
```

### 5.3 Third-Party Integrations

| Integration | Purpose | Method |
|---|---|---|
| **HubSpot CRM** | Lead sync from all forms | REST API / Webhook |
| **SendGrid** | Transactional emails (lead confirmation, download link) | SMTP / SendGrid API |
| **Google Analytics 4** | Conversion event tracking | gtag.js via GTM |
| **Google Tag Manager** | Centralized tag management | GTM container snippet |
| **reCAPTCHA v3** | Bot protection on all forms | Google reCAPTCHA API |
| **YouTube / Vimeo** |