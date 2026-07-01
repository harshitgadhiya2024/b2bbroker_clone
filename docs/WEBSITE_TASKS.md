# Comprehensive PRD, Website Audit & Clone Implementation Plan for B2Broker Website

**Website:** https://b2broker.com/
**Tech Stack Detected:** Next.js (React), Server-Side Rendering
**Pages Analyzed:** 8
**Date:** July 2, 2026
**Prepared by:** Petra, AI Product Manager — AI Employee OS

---

## Executive Summary

B2Broker is a Prime of Prime liquidity and technology provider serving forex brokers, crypto exchanges, and financial institutions. The website is a complex, multi-page marketing and product showcase built on Next.js. It features mega-menu navigation, multi-language support, lead-generation forms, a blog/insights CMS, product catalogs, interactive components (sliders, animations, tabs), and deep CTA conversion funnels. This document provides an exhaustive frontend and backend task breakdown for building a production-ready clone.

---

## Sitemap Overview

| # | Page | URL | Type |
|---|------|-----|------|
| 1 | Home | `/` | Dynamic Landing |
| 2 | Liquidity | `/products/liquidity/` | Product |
| 3 | Forex Broker Turnkey | `/products/forex-broker-turnkey/` | Product |
| 4 | Crypto Exchange Turnkey | `/products/cryptocurrency-exchange-turnkey/` | Product |
| 5 | Crypto Broker Turnkey | `/products/crypto-broker-turnkey/` | Product |
| 6 | B2CORE (Trader's Room) | `/products/b2core-traders-room/` | Product |
| 7 | Copy Trading Platform | `/products/copy-trading-platform/` | Product |
| 8 | B2CONNECT | `/products/b2connect/` | Product |

Additional pages inferred from navigation (to be built but not screenshotted): WhiteLabel, Services, Sectors, Blog, Company/About, Contact Us, Legal/Privacy, individual blog articles.

---

## Frontend Task List

---

### PAGE 1: HOME (`https://b2broker.com/`)

---

**Task-1: Home Page**
**Section-1: Hero — Forex, Crypto & CFD Prime of Prime Liquidity Provider**
**Task Title:** Build Home Hero Section with Animated Headline and CTA
**Description:** Implement a full-width hero section with a dark/gradient background. The headline "Forex, Crypto & CFD Prime of Prime Liquidity Provider" should render in large, bold white typography. Below the headline, add a subheading describing SaaS WhiteLabel Solutions. Include a prominent "Book a Demo" CTA button. Add subtle particle or animated background effects. The section must be fully responsive — stacking vertically on mobile with the CTA remaining prominent. Include the global top navigation bar (B2BROKER logo, mega-menu items: Liquidity, Turnkey, Products, WhiteLabel, Services, Sectors, Blog, Company, and a "Contact us" button).
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/0-forex--crypto---cfd-prime-of-p.png)

---

**Task-2: Home Page**
**Section-2: Product/Service Overview Cards**
**Task Title:** Build Product Highlights Grid Section
**Description:** Create a section displaying key product/service categories in a card-based or icon-grid layout. Each card should feature an icon or illustration, a product name, and a brief description. Cards should animate on scroll (fade-in or slide-up). Implement hover effects (subtle elevation, color shift). Layout should be a responsive grid — 3–4 columns on desktop, 2 on tablet, 1 on mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/1-.png)

---

**Task-3: Home Page**
**Section-3: Get Started — Lead Capture Form**
**Task Title:** Build "Get Started" Lead Generation Section with Email Form
**Description:** Implement a call-to-action section with a heading "Get Started", supporting copy, and an inline email capture form. The form should contain an email input field and a submit button. Include client-side validation (valid email format, required field). On submission, POST to the backend lead API and show a success/error toast notification. Style with a contrasting background color to stand out from adjacent sections.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/2-get-started.png)

---

**Task-4: Home Page**
**Section-4: Insights — Blog/Article Preview Cards**
**Task Title:** Build Insights/Blog Preview Carousel Section
**Description:** Build a section titled "Insights" that displays the latest blog articles in a horizontally scrollable carousel or grid. Each card must include a thumbnail image, article title (e.g., "What is Crypto Arbitrage?", "What is a Margin Call?"), a category tag, publication date, and a "Read more" link. Implement left/right navigation arrows for the carousel. Cards should link to individual blog post pages. Responsive: carousel on desktop, vertically stacked cards on mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/3-insights.png)

---

**Task-5: Home Page**
**Section-5: Statistics / Trust Indicators**
**Task Title:** Build Social Proof / Stats Counter Section
**Description:** Implement a section showcasing key metrics (e.g., 500+ clients, years in business, asset classes supported). Use animated number counters that trigger on scroll-into-view. Display each stat with an icon and label. Use a clean, horizontally distributed layout. Ensure counters only animate once per page load.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/4-.png)

---

**Task-6: Home Page**
**Section-6: Partners / Clients Logos Bar**
**Task Title:** Build Client Logo Marquee / Trust Bar Section
**Description:** Create a horizontal scrolling logo marquee or static grid displaying partner/client logos. Implement infinite horizontal scroll animation (marquee effect). Logos should be grayscale by default, turning to full color on hover. Ensure responsive behavior — fewer visible logos on smaller screens but maintaining the scroll effect.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/5-.png)

---

**Task-7: Home Page**
**Section-7: Explore Our Library — Resource Center Preview**
**Task Title:** Build Resource Library Preview Section
**Description:** Implement a section titled "Explore Our Library" that showcases downloadable resources (guides, whitepapers, e-books). Display each resource as a card with a cover image/thumbnail, title, type label, and a download/read CTA. Arrange in a responsive grid (3 columns desktop, 2 tablet, 1 mobile). Each card links to the resource detail page or triggers a lead-gated download modal.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/6-explore-our-library.png)

---

**Task-8: Home Page**
**Section-8: Featured Article — What is Crypto Arbitrage? / Footer Blog Highlights**
**Task Title:** Build Featured Article Highlight and Footer Section
**Description:** Build a featured article banner with a large preview image, article title "What is Crypto Arbitrage?", excerpt text, and a "Read More" CTA. Below or integrated, include the global site footer with: company logo, navigation links organized in columns (Products, Solutions, Company, Legal), social media icons, newsletter subscription input, copyright notice, and regulatory disclaimers. Footer must be responsive and consistent across all pages.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/home/7-what-is-crypto-arbitrage-.png)

---

### PAGE 2: LIQUIDITY (`https://b2broker.com/products/liquidity/`)

---

**Task-9: Liquidity Page**
**Section-1: Hero — One Margin Account for 10 Assets Classes**
**Task Title:** Build Liquidity Page Hero with Asset Class Tabs
**Description:** Implement the hero section with headline "One Margin Account for 10 Assets Classes". Below the headline, create a horizontal tab bar or pill navigation listing all 10 asset classes (Forex, Crypto, CFD, Metals, Indices, Energy, Commodities, NDFs, CFD Equities, ETFs, Fixed Income). Each tab click should reveal asset-specific details, margin specifications, and descriptive content below. Include a "Margin Specifications" link and a "Book a Demo" CTA. Add a sub-navigation bar specific to the Liquidity page (Assets, Licenses, Prime of Prime, Connectivity, FAQ, Book a Demo).
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/0-one-margin-account-for-10-asse.png)

---

**Task-10: Liquidity Page**
**Section-2: Asset Class Details / Specifications Grid**
**Task Title:** Build Asset Specifications Data Grid
**Description:** Build a detailed specifications section showing liquidity parameters per asset class — margin requirements, spreads, available instruments count. Display as a responsive data table or card grid. Include filter/tab interaction linked to the hero tabs above. Each asset card should show key stats (e.g., "0.5% Margin Requirement for Forex"). Add subtle hover effects and ensure mobile horizontal scrolling for tables.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/1-.png)

---

**Task-11: Liquidity Page**
**Section-3: Customer Trust — 500+ Customers Social Proof (Part 1)**
**Task Title:** Build Customer Count and Trust Headline Section
**Description:** Implement a full-width banner section with the headline "500+ customers trust our industry scalable solutions, advanced technology and exceptional support". Include animated counter for the 500+ number. Add supporting descriptive text about reliability and scalability. Background should feature a gradient or subtle pattern. Center-aligned text, responsive typography.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/2-500--customers-trust-our-indus.png)

---

**Task-12: Liquidity Page**
**Section-4: Customer Testimonials / Client Logos (Part 2)**
**Task Title:** Build Client Testimonials or Logos Grid
**Description:** Build a companion section displaying client logos, testimonial quotes, or case study references. Use a grid or carousel format. Each item may include a company logo, a quote, and attribution. Implement carousel auto-play with pause-on-hover. Responsive: 2–3 columns on desktop, single column on mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/3-500--customers-trust-our-indus.png)

---

**Task-13: Liquidity Page**
**Section-5: Get Started CTA**
**Task Title:** Build Liquidity Page "Get Started" CTA Section
**Description:** Implement a CTA section with heading "Get Started", brief description of onboarding steps, and a prominent email capture form or "Book a Demo" button. Reuse the shared lead capture form component from Task-3 but allow page-specific styling overrides (different background color/image). Submit to the same lead API with a page-source identifier.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/4-get-started.png)

---

**Task-14: Liquidity Page**
**Section-6: Strategic Advantages**
**Task Title:** Build Strategic Advantages Feature Grid
**Description:** Create a section titled "Strategic Advantages" displaying competitive differentiators in a multi-column icon+text card layout. Each advantage should have an icon/illustration, a bold title, and 2–3 lines of description. Animate cards on scroll (staggered fade-in). Grid: 3 columns desktop, 2 tablet, 1 mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/5-strategic-advantages.png)

---

**Task-15: Liquidity Page**
**Section-7: STP Agency Model**
**Task Title:** Build STP Agency Model Explainer Section
**Description:** Implement an explanatory section for the STP Agency Model with a diagram or flowchart illustration showing how trades are routed directly to the market. Include heading, descriptive paragraph, and a visual (static image or animated SVG diagram). Add supporting bullet points about transparency and no conflict of interest. Layout: image on one side, text on the other (alternating left/right pattern).
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/6-stp-agency-model.png)

---

**Task-16: Liquidity Page**
**Section-8: Transparency**
**Task Title:** Build Transparency Section with Licensing Details
**Description:** Build a section focused on transparency and regulation. Display license information cards (Investment Dealer License, Investment Firm License, Investment Bank License, Securities Dealer License) with issuing authority, license number, and status. Each license card should be visually distinct, possibly with a badge or seal icon. Include a heading "Licences & Regulation" and supporting copy. Responsive card grid layout.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-liquidity/7-transparency.png)

---

### PAGE 3: FOREX BROKER TURNKEY (`https://b2broker.com/products/forex-broker-turnkey/`)

---

**Task-17: Forex Broker Turnkey Page**
**Section-1: Hero — Start a FOREX BROKER with our Turnkey Solution**
**Task Title:** Build Forex Turnkey Hero Section
**Description:** Implement a hero section with headline "Start a FOREX BROKER with our Turnkey Solution", subtext, and two CTAs: "Book a Demo" and "Try Demo". Include the page-specific sub-navigation (Overview, Components, Advantages, Roadmap, Solution, Mobile App, Offers). Background should feature a dark/tech-themed gradient or abstract graphic. Responsive with stacked CTAs on mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/0-start-a-forex-broker-with-our-.png)

---

**Task-18: Forex Broker Turnkey Page**
**Section-2: B2CORE Component Card (Part 1)**
**Task Title:** Build Turnkey Components Showcase — B2CORE Card
**Description:** Build a product component card for "B2CORE — FOREX CRM and Back Office, Client's Cabinet". The card should feature a product icon/logo, title, brief description, and a link to the B2CORE product page. Include a screenshot or UI mockup image within the card. Part of a larger component grid showing all included turnkey components (B2CORE, B2TRADER, CTRADER WL, LIQUIDITY, B2BINPAY, B2COPY, MT* Services).
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/1-b2core.png)

---

**Task-19: Forex Broker Turnkey Page**
**Section-3: B2CORE Detailed Feature Breakdown (Part 2)**
**Task Title:** Build B2CORE Feature Detail Expansion
**Description:** Implement a detailed feature breakdown for B2CORE showing sub-features like client cabinet, back-office management, KYC integration, payment processing. Use an expandable accordion or tabbed interface. Each feature should have an icon, title, and description. Include a product screenshot or platform UI preview image. Layout: split-screen with text left and image right, or a tabbed panel.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/2-b2core.png)

---

**Task-20: Forex Broker Turnkey Page**
**Section-4: Track Record — 10 Years, 500+ Clients (Part 1)**
**Task Title:** Build Company Track Record Stats Section
**Description:** Create a section highlighting the company's track record: "For 10 years, we've helped over 500 clients launch FOREX Brokers. As the largest…". Display key statistics with animated counters (10+ years, 500+ clients, number of asset classes). Use a visually impactful layout with large numbers, supporting text, and possibly a timeline or milestone visualization.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/3-for-10-years--we-ve-helped-ove.png)

---

**Task-21: Forex Broker Turnkey Page**
**Section-5: Track Record Continued (Part 2)**
**Task Title:** Build Extended Track Record / Advantages List
**Description:** Continue the track record section with additional detail — list of key advantages, competitive differentiators, or client success metrics. Use icon+text rows or an infographic-style layout. Include references to technology partnerships and integration capabilities. Smooth scroll-triggered animations.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/4-for-10-years--we-ve-helped-ove.png)

---

**Task-22: Forex Broker Turnkey Page**
**Section-6: STP Agency Model Explainer**
**Task Title:** Build STP Model Section for Forex Turnkey
**Description:** Implement a section explaining the STP agency model: "Rely on our STP agency model that routes trades directly to the market with no conflict of interest." Include a flow diagram or infographic showing the order routing process. Use alternating layout (image+text). Add supporting bullet points about execution quality, transparency, and direct market access.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/5-rely-on-our-stp-agency-model-t.png)

---

**Task-23: Forex Broker Turnkey Page**
**Section-7: Roadmap / Implementation Timeline**
**Task Title:** Build Implementation Roadmap Visual Section
**Description:** Create a visual roadmap or timeline showing the steps to launch a forex brokerage — from onboarding through go-live. Use a horizontal or vertical timeline component with step numbers, titles, descriptions, and estimated timeframes. Each step should be visually connected (line/connector). Include icons for each phase. Responsive: horizontal timeline on desktop, vertical on mobile.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/6-.png)

---

**Task-24: Forex Broker Turnkey Page**
**Section-8: Pricing / Offers / CTA**
**Task Title:** Build Pricing Tiers or Offers Comparison Section
**Description:** Implement a section displaying turnkey solution offers or pricing tiers. Use a comparison table or pricing card layout (e.g., Basic, Advanced, Enterprise). Each tier shows included features with checkmarks, pricing indication, and a "Book a Demo" or "Get Quote" CTA. Include a "Contact Sales" fallback. Responsive: cards stack on mobile with a sticky CTA.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-forex-broker-turnkey/7-.png)

---

### PAGE 4: CRYPTO EXCHANGE TURNKEY (`https://b2broker.com/products/cryptocurrency-exchange-turnkey/`)

---

**Task-25: Crypto Exchange Turnkey Page**
**Section-1: Hero — Launch a Cryptocurrency Exchange with our Turnkey Solution**
**Task Title:** Build Crypto Exchange Hero Section
**Description:** Implement hero with headline "Launch a Cryptocurrency Exchange with our Turnkey Solution", subheading about fast, compliant, high-performance exchange, and "Book a Demo" CTA. Include page sub-navigation (About, Components, Multi-Account, Leverages, Liquidity, Mobile App, Features). Dark background with tech/crypto-themed graphics or animations.
![Section Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782921996/products-cryptocurrency-exchange-turnkey/0-launch-a-cryptocurrency-exchan.png)

---

**Task-26: Crypto Exchange Turnkey Page**
**Section-2: Platform Overview / Components