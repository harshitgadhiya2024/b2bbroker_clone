# PRD: Comprehensive PRD, Website Audit & Clone Implementation Plan for B2Broker Website

**Document Version:** 1.1
**Date:** July 2, 2026
**Author:** Petra, AI Product Manager — AI Employee OS
**Website Under Analysis:** https://b2broker.com/
**Status:** Ready for Engineering Review

---

## 1. Executive Summary

### 1.1 Overview

B2Broker is a global Prime of Prime (PoP) liquidity and technology provider serving forex brokers, crypto exchanges, banks, hedge funds, and payment providers. The website acts as the company's primary commercial hub — combining corporate marketing, product catalogs, lead generation, educational content, and partner onboarding into a single, high-performance web property.

The clone will use **Next.js** purely as a frontend framework (SSR/SSG/ISR for SEO and performance) and **FastAPI (Python)** as the dedicated backend API server. This separation keeps the frontend lightweight and focused on rendering while the backend handles all business logic, form processing, CRM integration, and data orchestration. A headless CMS (Strapi) manages editorial content independently.

### 1.2 Scope of the Clone Project

This PRD defines the full requirements for building a **production-ready clone** that replicates:

- All public-facing pages, navigation, and content structure
- The product catalog architecture (Liquidity, Turnkey Solutions, White Label, individual products)
- The blog/insights CMS with category filtering and search
- The resource/library section with downloadable assets
- Lead generation workflows (demo booking, contact forms, newsletter)
- Multi-language infrastructure
- SEO structure (URL patterns, meta tags, schema markup, sitemap)
- Responsive, mobile-first UI with animations, sliders, and video embeds
- Admin panel for content and lead management

### 1.3 Business Objectives

| Objective | Success Metric |
|---|---|
| Feature parity with b2broker.com | 95%+ of public pages and workflows replicated |
| SEO-ready architecture | Lighthouse SEO score ≥ 95 |
| Performance | Core Web Vitals passing on mobile and desktop |
| Content independence | Non-technical staff can manage all content via CMS |
| Lead capture | All forms submit to CRM pipeline with email confirmation |
| Launch readiness | Deployable to production within defined timeline |

### 1.4 Project Estimation Summary

| Metric | Value |
|---|---|
| Total estimated pages (unique templates) | 45–55 |
| Static pages | ~15 |
| Dynamic / CMS-driven pages | ~35–40 |
| Landing pages | ~8–10 |
| Blog/news articles (template × n entries) | 1 template, 200+ entries |
| Product pages | ~12–15 |
| Legal/compliance pages | ~5 |
| MVP timeline | 10–12 weeks |
| Full production timeline | 18–22 weeks |
| Core team size | 6–8 engineers + 1 PM + 1 designer |

---

## 2. Tech Stack Recommendation

### 2.1 Frontend

| Layer | Technology | Justification |
|---|---|---|
| Framework | **Next.js 14+ (App Router)** | Used strictly as a frontend/rendering framework. Preserves SSR/SSG capabilities, ISR for blog content, excellent SEO support via metadata API, and React Server Components for performance. No API routes or backend logic lives here. |
| Language | **TypeScript** | Type safety across a large component library reduces defects, improves maintainability, and enables better IDE tooling for the team. |
| Styling | **Tailwind CSS + CSS Modules** | Utility-first approach accelerates responsive development. CSS Modules handle component-scoped custom animations. Matches the dense, utility-driven styling patterns visible on the original site. |
| Animation | **Framer Motion** | Handles the scroll-triggered reveals, section transitions, and interactive hover states present throughout the B2Broker site. |
| Carousel/Slider | **Swiper.js** | Powers the testimonial sliders, product showcases, and partner logo carousels observed on multiple pages. |
| Icons | **Lucide React + custom SVGs** | Lightweight icon set supplemented by brand-specific SVG assets. |
| State Management | **Zustand** | Lightweight, sufficient for UI state (language selector, mobile menu, form state). No heavy global state needed for a primarily content-driven site. |
| Forms | **React Hook Form + Zod** | Performant form handling with schema-based validation for all lead capture forms. |

### 2.2 Backend

| Layer | Technology | Justification |
|---|---|---|
| API / Server | **FastAPI** | Dedicated Python backend, fully decoupled from the Next.js frontend. Handles form submissions, newsletter signups, demo booking orchestration, CRM webhook dispatch, email triggers, and any custom business logic. Provides auto-generated OpenAPI docs (`/docs`) for frontend integration. |
| Language | **Python 3.12+** | Mature ecosystem for API development, data processing, and third-party service integrations. Strong library support for CRM SDKs, email services, and search indexing. |
| Validation | **Pydantic v2** | Schema-based request/response validation with automatic serialization, tightly integrated with FastAPI. |
| ASGI Server | **Uvicorn + Gunicorn** | Uvicorn as the ASGI worker for async performance; Gunicorn as the process manager for production deployments. |
| ORM / DB Access | **SQLAlchemy 2.0 + Alembic** | Async-capable ORM for PostgreSQL access. Alembic handles database migrations. |
| CMS | **Strapi v5 (Headless)** | Open-source headless CMS provides the admin panel, content modeling, media management, role-based access, and i18n plugin for multi-language. Self-hosted for data control. The Next.js frontend fetches content from Strapi directly; FastAPI handles non-content business logic. Alternatives: Payload CMS if tighter Next.js integration is preferred. |
| Email Service | **Resend (via Python SDK) or SendGrid** | Transactional emails for form confirmations, demo booking receipts. SendGrid if marketing automation (drip campaigns) is needed. Both provide Python client libraries. |
| Search | **Meilisearch** | Fast, typo-tolerant full-text search for blog articles, products, and resources. FastAPI manages index synchronization and exposes search endpoints to the frontend. Lightweight self-hosted alternative to Algolia. |
| Task Queue (optional) | **Celery + Redis** | For async background tasks such as CRM sync, email dispatch, and search re-indexing. Only needed if synchronous processing introduces latency. |

### 2.3 Database

| Layer | Technology | Justification |
|---|---|---|
| Primary Database | **PostgreSQL 16** | Battle-tested relational DB. Used by both Strapi (content) and FastAPI (leads, form submissions, application data). Handles structured content, user accounts, leads, and relational product data. |
| Cache | **Redis** | Session storage, API response caching, rate limiting, and Celery broker if task queue is adopted. |
| File/Media Storage | **AWS S3 or Cloudflare R2** | Stores uploaded media, downloadable PDFs, and video thumbnails. R2 preferred for zero-egress cost. |

### 2.4 Infrastructure & DevOps

| Layer | Technology | Justification |
|---|---|---|
| Hosting (Frontend) | **Vercel** | Native Next.js hosting with edge functions, ISR, preview deployments, and built-in analytics. Zero-config deployment. Next.js runs here as a pure frontend — no API routes. |
| Hosting (Backend API) | **AWS EC2 / Railway / Render** | FastAPI runs as a containerized Python service (Docker + Uvicorn/Gunicorn). Railway or Render for simplicity; EC2 for full control. |
| Hosting (CMS) | **AWS EC2 / Railway / Render** | Strapi runs as a standalone Node.js service, separate from both the frontend and the FastAPI backend. |
| CDN | **Vercel Edge Network or Cloudflare** | Global CDN for static assets, images, and cached pages. |
| CI/CD | **GitHub Actions** | Automated lint, test, build, deploy pipeline. Preview deployments on PRs via Vercel (frontend). Separate pipelines for FastAPI and Strapi containers. |
| Monitoring | **Sentry (errors) + Vercel Analytics (performance)** | Error tracking across both frontend (JS) and backend (Python). Core Web Vitals monitoring via Vercel. |
| Container | **Docker + Docker Compose** | Containerized FastAPI, Strapi, PostgreSQL, Redis, and Meilisearch for consistent dev/staging/prod environments. |

### 2.5 Third-Party Services

| Service | Purpose |
|---|---|
| **Google Analytics 4 + GTM** | User tracking, conversion tracking, event analytics |
| **HubSpot or Salesforce** | CRM integration for lead routing from demo booking and contact forms (FastAPI dispatches leads via CRM API/SDK) |
| **Calendly or Cal.com** | Demo booking scheduling (embedded on frontend or API-integrated via FastAPI) |
| **Cookiebot or OneTrust** | GDPR/cookie consent management |
| **Cloudinary** (optional) | Image optimization and transformation CDN |
| **Recaptcha v3 or Turnstile** | Bot protection on all public forms (token verified server-side by FastAPI) |

### 2.6 Architecture Diagram (Logical)

```
┌─────────────────────────────────────────────────────────┐
│                      End Users / Browsers               │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│              Vercel (Next.js Frontend)                   │
│  SSR / SSG / ISR — rendering only, no business logic    │
│  Fetches content from Strapi, calls FastAPI for actions  │
└──────────┬──────────────────────────┬───────────────────┘
           │                          │
           ▼                          ▼
┌─────────────────────┐   ┌─────────────────────────────┐
│   Strapi v5 (CMS)   │   │   FastAPI (Backend API)     │
│   Content CRUD,      │   │   Form handling, CRM sync,  │
│   Media, i18n        │   │   Email, Search, Auth,      │
│   Admin Panel        │   │   Webhooks, Business Logic  │
└──────────┬──────────┘   └──────────┬──────────────────┘
           │                          │
           ▼                          ▼
┌─────────────────────────────────────────────────────────┐
│                    PostgreSQL 16                         │
│         (Strapi DB + Application DB schemas)            │
└─────────────────────────────────────────────────────────┘
           │
     ┌─────┴─────┐
     ▼           ▼
  Redis      Meilisearch      S3 / R2
 (Cache)     (Search Index)   (Media)
```

---

## 3. Site Structure & Pages

### 3.1 Complete Sitemap

The following sitemap is derived from the analyzed pages, navigation links, and inferred structure from the B2Broker website. Pages are grouped by category.

#### 3.1.1 Top-Level / Corporate Pages

| # | URL Path | Page Title / Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 1 | `/` | Homepage — Hero, value propositions, product overview, insights, partner logos, CTAs | Hero with animated text, product grid, insights carousel, partner logo slider, newsletter form, mega-menu navigation | Dynamic (CMS-driven insights, partner logos) |
| 2 | `/company/about/` | About B2Broker — Company history, mission, team, global offices | Timeline component, team grid, office map, stats counters | Static with minor CMS fields |
| 3 | `/company/careers/` | Careers — Open positions, culture, benefits | Job listing feed (dynamic), culture gallery, benefits grid | Dynamic |
| 4 | `/company/events/` | Events — Upcoming and past industry events | Event cards with date/location filters | Dynamic |
| 5 | `/company/news/` | Press/News — Company announcements | News article listing with pagination | Dynamic |
| 6 | `/company/partners/` | Partners — Partner program overview, partner logos | Partner tier grid, application CTA | Semi-static |
| 7 | `/company/contact/` | Contact Us — Global offices, contact form | Contact form, office address cards with map embeds | Static + form |
| 8 | `/legal/privacy-policy/` | Privacy Policy | Long-form legal text | Static |
| 9 | `/legal/terms-of-use/` | Terms of Use | Long-form legal text | Static |
| 10 | `/legal/cookie-policy/` | Cookie Policy | Long-form legal text | Static |
| 11 | `/legal/aml-policy/` | AML Policy | Long-form legal text | Static |
| 12 | `/legal/risk-disclosure/` | Risk Disclosure | Long-form legal text | Static |

#### 3.1.2 Product Pages — Liquidity

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 13 | `/products/liquidity/` | Liquidity Hub — 10 asset classes overview, margin specs, licenses, connectivity | Sub-navigation (Assets, Licenses, PoP, Connectivity, FAQ), asset class tabs, margin specification tables, license cards, CTA "Book a Demo" | Dynamic (specs from CMS) |
| 14 | `/products/liquidity/forex/` | Forex Liquidity — Spreads, pairs, specs | Data tables, spread comparison, downloadable spec sheet | Dynamic |
| 15 | `/products/liquidity/crypto/` | Crypto Liquidity | Token pair listings, real-time spread examples | Dynamic |
| 16 | `/products/liquidity/cfd/` | CFD Liquidity | Instrument tables | Dynamic |
| 17 | `/products/liquidity/metals/` | Metals Liquidity | Spec tables | Dynamic |
| 18 | `/products/liquidity/indices/` | Indices Liquidity | Spec tables | Dynamic |
| 19 | `/products/liquidity/energy/` | Energy Liquidity | Spec tables | Dynamic |
| 20 | `/products/liquidity/commodities/` | Commodities Liquidity | Spec tables | Dynamic |
| 21 | `/products/liquidity/ndfs/` | NDFs Liquidity | Spec tables | Dynamic |
| 22 | `/products/liquidity/equities/` | CFD Equities Liquidity | Spec tables | Dynamic |
| 23 | `/products/liquidity/etfs/` | ETFs Liquidity | Spec tables | Dynamic |

#### 3.1.3 Product Pages — Turnkey Solutions

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 24 | `/products/forex-broker-turnkey/` | Forex Broker Turnkey — Complete brokerage launch package | Sub-nav (Overview, Components, Advantages, Roadmap, Solution, Mobile App, Offers), product component cards (B2Core, B2Trader, cTrader WL, Liquidity, B2BinPay, B2Copy), roadmap timeline, pricing tier cards | Dynamic (CMS components, offers) |
| 25 | `/products/cryptocurrency-exchange-turnkey/` | Crypto Exchange Turnkey — Launch a crypto exchange | Sub-nav (About, Components, Multi-Account, Leverages, Liquidity, Mobile App, Features), feature matrix, mobile app showcase | Dynamic |
| 26 | `/products/margin-exchange-turnkey/` | Margin Exchange Turnkey | Similar structure to crypto exchange | Dynamic |
| 27 | `/products/social-broker-turnkey/` | Social/Copy Trading Broker Turnkey | Component overview, social trading features | Dynamic |
| 28 | `/products/prop-trading-turnkey/` | Prop Trading Turnkey | Prop firm specific features, challenge flow | Dynamic |

#### 3.1.4 Product Pages — Individual Products

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 29 | `/products/b2core/` | B2Core — CRM and Back Office Platform | Feature breakdown, screenshots, integration diagram | Dynamic |
| 30 | `/products/b2trader/` | B2Trader — Trading Platform | Platform specs, screenshots, asset support | Dynamic |
| 31 | `/products/b2binpay/` | B2BinPay — Crypto Payment Gateway | Supported currencies, fee structure, integration guide | Dynamic |
| 32 | `/products/b2copy/` | B2Copy — Copy/Social Trading Platform | Feature list, architecture diagram | Dynamic |

#### 3.1.5 White Label Pages

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 33 | `/whitelabel/` | White Label Solutions Hub | Solution cards, comparison matrix | Semi-static |
| 34 | `/whitelabel/ctrader/` | cTrader White Label | Feature set, pricing, screenshots | Dynamic |
| 35 | `/whitelabel/b2trader/` | B2Trader White Label | Feature set, pricing | Dynamic |

#### 3.1.6 Services Pages

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 36 | `/services/` | Services Overview | Service category cards | Semi-static |
| 37 | `/services/mt-services/` | MetaTrader Services | MT4/MT5 admin, hosting, plugins | Dynamic |
| 38 | `/services/ib-program/` | IB/Affiliate Program | Commission tiers, registration CTA | Dynamic |

#### 3.1.7 Sector / Industry Pages

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 39 | `/sectors/forex-brokers/` | For Forex Brokers | Sector-specific value props, relevant product CTAs | Semi-static |
| 40 | `/sectors/crypto-exchanges/` | For Crypto Exchanges | Sector-specific value props | Semi-static |
| 41 | `/sectors/banks/` | For Banks | Sector-specific value props | Semi-static |
| 42 | `/sectors/hedge-funds/` | For Hedge Funds | Sector-specific value props | Semi-static |

#### 3.1.8 Blog & Resource Pages

| # | URL Path | Purpose | Key Components | Static/Dynamic |
|---|---|---|---|---|
| 43 | `/blog/` | Blog/Insights Hub — Article listing | Category filters, search, pagination, featured article hero | Dynamic (CMS) |
| 44 | `/blog/[slug]/` | Individual Blog Article | Article body (rich text), author card, related articles, social share, TOC sidebar | Dynamic (CMS) |
| 45 | `/library/` | Resource Library — Guides, whitepapers, videos | Resource cards with type filters (video, PDF, guide), download gating | Dynamic (CMS) |
| 46 | `/library/[slug]/` | Individual Resource Page | Resource detail, download/view CTA, related resources | Dynamic (CMS) |