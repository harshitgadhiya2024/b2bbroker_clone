# Analyze Entire B2Broker Website and Generate Frontend + Backend Development Task Breakdown

---

## Frontend Task List

---

**Task-1: Home Page**
**Section-1: Hero / Main Banner**
**Task Title**: Build Full-Width Hero Section with Animated Headline and CTA
**Description**: Implement a full-width hero section with a bold headline "Forex, Crypto & CFD Prime of Prime Liquidity Provider", a subheadline about SaaS WhiteLabel Solutions, and two CTA buttons ("Book a Demo", "Get Started"). Include animated background (particle/globe effect or gradient mesh), responsive layout for mobile/tablet/desktop, and smooth entrance animations using Framer Motion or CSS keyframes. Navigation bar with mega-menu dropdowns for Liquidity, Turnkey, Products, WhiteLabel, Services, Sectors, Blog, Company plus a sticky "Contact us" button.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-2: Home Page**
**Section-2: Liquidity Provision – Asset Classes Tabs**
**Task Title**: Build Interactive Multi-Asset Tabs Component
**Description**: Build a horizontally scrollable tab bar listing 10 asset classes (Forex, Crypto, CFD, Metals, Indices, Energy, Commodities, NDFs, CFD Equities, ETFs). Each tab click reveals a content panel with specs, margin requirements, and a brief description. Animate tab indicator underline on selection. Use lazy loading for panel content. Ensure keyboard-accessible tab navigation and ARIA roles.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-3: Home Page**
**Section-3: "Get Started" Lead Capture Form**
**Task Title**: Build Inline Email Lead Capture Form with Validation
**Description**: Implement a centered section with headline "Get Started", a single email input field, and a submit CTA button. Add real-time inline validation (invalid email format, empty field). On success, show a toast/inline confirmation message. Connect to backend lead submission API. Style matches brand (dark background, gold/blue accent).
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-4: Home Page**
**Section-4: Insights / Blog Preview Cards**
**Task Title**: Build Blog Insights Grid with Article Cards
**Description**: Implement a 3-column responsive grid of blog article preview cards. Each card contains: featured image, category tag, article title, short excerpt, and "Read More" link. Cards include hover elevation effect (box-shadow lift). Section has a heading "Insights" and a "Explore Our Library" CTA button linking to the blog index. Fetch data dynamically from Blog API. Handle loading skeletons and empty state.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-5: Home Page**
**Section-5: Media About Us / Press Logos**
**Task Title**: Build Auto-Scrolling Media Logos Marquee
**Description**: Implement an infinite horizontal marquee/carousel of media outlet logos (press mentions). Use CSS animation or a lightweight JS library. Logos should be monochrome by default, color on hover. Include a section heading "Media About Us". Ensure the loop is seamless and pauses on hover for accessibility.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-6: Home Page**
**Section-6: Footer**
**Task Title**: Build Multi-Column Footer with Navigation, Socials & Legal Links
**Description**: Build a full-width footer with 4–5 columns: product/service link groups (Liquidity, Turnkey, Products, WhiteLabel, Services), Company links, Blog, and a contact/social column. Include social media icons (LinkedIn, Twitter, Telegram, YouTube). Bottom bar includes copyright text, Privacy Policy, and Terms links. Fully responsive — columns stack on mobile.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/home.png)

---

**Task-7: Liquidity Page (`/products/liquidity/`)**
**Section-1: Hero – One Margin Account for 10 Asset Classes**
**Task Title**: Build Liquidity Page Hero with Asset Class Tab Selector
**Description**: Full-width hero with headline "One Margin Account for 10 Assets Classes", animated asset-class pill/tab row (Forex, Crypto, CFD, Metals, Indices, Energy, Commodities, NDFs, CFD Equities, ETFs, Fixed Income). Each pill filters displayed margin specifications in a data table below. Include "Book a Demo" CTA. Sticky secondary nav: Assets, Licenses, Prime of Prime, Connectivity, FAQ, Book a Demo.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-8: Liquidity Page**
**Section-2: Trust Stats Bar**
**Task Title**: Build Animated Statistics Counter Row
**Description**: Implement a horizontal stats band showing key metrics (e.g., "500+ customers", uptime %, asset classes count). Each number animates counting up when scrolled into viewport using Intersection Observer API. Icons accompany each stat. Dark/gradient background with white text.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-9: Liquidity Page**
**Section-3: Licences & Regulation**
**Task Title**: Build Regulatory Licences Cards Grid
**Description**: Build a grid of regulatory licence cards, each showing: licence name (e.g., "Investment Dealer License", "Investment Firm License"), jurisdiction flag/icon, short description, and a badge indicator. Cards use subtle border and hover highlight. Section includes a heading "Licencies & Regulation" and introductory paragraph. Data fetched from CMS/API.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-10: Liquidity Page**
**Section-4: Strategic Advantages**
**Task Title**: Build Feature Highlights with Icon + Text Columns
**Description**: Three-column layout (or alternating left/right on mobile) highlighting strategic advantages: STP Agency Model, Deep Liquidity Pool with Low Market Impact, Transparency. Each item has an icon, bold title, and 2–3 sentence description. Animate items in on scroll with staggered fade-up.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-11: Liquidity Page**
**Section-5: Technologies & Infrastructure / World-Class Infrastructure**
**Task Title**: Build Technology Stack Diagram Section
**Description**: Build a visual infrastructure diagram section showing connectivity layers, servers, and data flow (as SVG or image with hotspot tooltips). Include a "World-Class Infrastructure" heading, supporting paragraphs, and a Connectivity subsection listing supported bridges/protocols. Tooltips on diagram nodes expand with descriptive text.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-12: Liquidity Page**
**Section-6: Start Your Forex Brokerage CTA Banner**
**Task Title**: Build Bottom CTA Banner with Email Form
**Description**: Full-width dark CTA section: "Start Your Forex Brokerage in a short time frame", supporting text, and inline email capture form. Matches design from homepage form. Connects to same lead generation backend API endpoint.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-liquidity.png)

---

**Task-13: Forex Broker Turnkey Page (`/products/forex-broker-turnkey/`)**
**Section-1: Hero – Start a Forex Broker**
**Task Title**: Build Turnkey Forex Broker Hero Section
**Description**: Hero with bold headline "Start a FOREX BROKER with our Turnkey Solution", subheadline, and dual CTAs ("Book a Demo", "Try Demo"). Include a visual product stack diagram showing components: B2CORE, B2TRADER, CTRADER WL, LIQUIDITY, B2BINPAY, B2COPY, MT* Services. Sticky secondary nav: Overview, Components, Advantages, Roadmap, Solution, Mobile App, Offers.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-forex-broker-turnkey.png)

---

**Task-14: Forex Broker Turnkey Page**
**Section-2: Turnkey Components Showcase**
**Task Title**: Build Interactive Component Cards for Turnkey Stack
**Description**: Grid/row of product component cards, one per component (B2CORE, B2TRADER, cTrader WL, Liquidity, B2BinPay, B2COPY, MT* Services). Each card has logo, one-line description, and a "Learn More" link. Clicking expands an inline drawer or navigates to product sub-page. Animate cards in with stagger on scroll.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-forex-broker-turnkey.png)

---

**Task-15: Forex Broker Turnkey Page**
**Section-3: Benefits / Advantages**
**Task Title**: Build Advantages Icon-List Section
**Description**: Multi-column section listing brokerage turnkey advantages: STP agency model, deep liquidity pool, cost-effective solution, 24/7/365 multilingual support. Each advantage has an icon, title, and description. Use a 2×2 or 3-column responsive grid. Subtle background pattern differentiates the section.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-forex-broker-turnkey.png)

---

**Task-16: Forex Broker Turnkey Page**
**Section-4: Brokerage Flow Diagram**
**Task Title**: Build Interactive Brokerage Flow / Architecture Diagram
**Description**: SVG or image-based flow diagram showing the brokerage operational flow (client → trading platform → CRM → liquidity → market). Hotspot nodes expand tooltips with component descriptions. Include a "More on our YouTube channel" embedded video thumbnail CTA.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-forex-broker-turnkey.png)

---

**Task-17: Forex Broker Turnkey Page**
**Section-5: Cost Savings / Salaries Calculator**
**Task Title**: Build Cost Comparison and Savings Banner
**Description**: Section with headline "Building a brokerage from scratch can be costly – We save you millions". Include a salary/cost comparison table or visual infographic contrasting in-house build costs vs. turnkey costs. Animate numbers on scroll. Include a CTA to "Book a Demo" at the bottom.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-forex-broker-turnkey.png)

---

**Task-18: Crypto Exchange Turnkey Page (`/products/cryptocurrency-exchange-turnkey/`)**
**Section-1: Hero – Launch a Cryptocurrency Exchange**
**Task Title**: Build Crypto Exchange Turnkey Hero Section
**Description**: Full-width hero with headline "Launch a Cryptocurrency Exchange with our Turnkey Solution", animated crypto/blockchain background visual, and CTAs "See our products in action right now" (demo link) and "Book a Demo". Secondary nav similar to Forex Turnkey page. Responsive design with mobile-first layout.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-cryptocurrency-exchange-turnkey.png)

---

**Task-19: Crypto Exchange Turnkey Page**
**Section-2: All-in-One Simple Mobile App**
**Task Title**: Build Mobile App Preview Section with Device Mockup
**Description**: Side-by-side layout: left side shows a phone mockup with app UI screenshots (using CSS 3D perspective or device frame library), right side has heading "All-in-One Simple Mobile App", feature bullet points, and an App Store / Google Play CTA badge row. Implement auto-rotating screenshot carousel inside the device frame.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-cryptocurrency-exchange-turnkey.png)

---

**Task-20: Crypto Exchange Turnkey Page**
**Section-3: Exchange Features Grid**
**Task Title**: Build Feature Highlights Grid for Crypto Exchange
**Description**: 3–4 column icon+text grid enumerating exchange capabilities (spot trading, margin, staking, matching engine, liquidity, KYC/AML integration, multi-currency wallets, API access). Each cell has icon, title, short description. Section uses alternating dark/light card backgrounds. Animate on scroll.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-cryptocurrency-exchange-turnkey.png)

---

**Task-21: Crypto Exchange Turnkey Page**
**Section-4: Lead Capture CTA / Email Form**
**Task Title**: Build Crypto Exchange Page Bottom CTA with Form
**Description**: Bottom-of-page CTA banner with email capture form. Headline encouraging action, email input, submit button. Same component pattern as other pages but with crypto-themed visual accent. Validate email on submit and display success/error states.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-cryptocurrency-exchange-turnkey.png)

---

**Task-22: Crypto Broker Turnkey Page (`/products/crypto-broker-turnkey/`)**
**Section-1: Hero – Ready-Made Crypto Brokerage Solution**
**Task Title**: Build Crypto Broker Turnkey Hero
**Description**: Hero section with headline introducing BBP's ready-made crypto broker solution, supporting subheadline, hero visual (platform/dashboard mockup), and dual CTAs. Sticky secondary nav matching product page pattern. Dark theme with crypto-accent color palette.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-crypto-broker-turnkey.png)

---

**Task-23: Crypto Broker Turnkey Page**
**Section-2: Solution Components & Features**
**Task Title**: Build Component Feature Cards for Crypto Broker Stack
**Description**: Card grid listing solution components specific to crypto brokerage (CRM, trading platform, liquidity bridge, payment gateway, white-label app). Each card: icon, title, 2-line description, "Learn More" link. Responsive 2–3 column grid.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-crypto-broker-turnkey.png)

---

**Task-24: Crypto Broker Turnkey Page**
**Section-3: Advantages and CTA**
**Task Title**: Build Advantages List and Bottom CTA for Crypto Broker Page
**Description**: Vertical or 2-column list of competitive advantages (fast launch, low cost, regulated, full support). Each item with check-icon and descriptive text. Ends with a prominent "Book a Demo" CTA button and email form section.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-crypto-broker-turnkey.png)

---

**Task-25: B2CORE Trader's Room Page (`/products/b2core-traders-room/`)**
**Section-1: Hero – Advanced Forex CRM**
**Task Title**: Build B2CORE Product Hero Section
**Description**: Hero with headline "Advanced Forex CRM Solutions", product badge/logo, dashboard UI screenshot as hero visual, and CTAs "Book a Demo" / "Learn More". Sticky sub-nav: Overview, Features, Integrations, Technology, Pricing/Offers. Background with subtle dark gradient.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-b2core-traders-room.png)

---

**Task-26: B2CORE Page**
**Section-2: Key Features Grid**
**Task Title**: Build B2CORE Feature Highlights Grid
**Description**: 3-column grid of B2CORE feature cards: KYC/AML, Multi-Account Management, Payment Gateway Integration, IB Management, Reports & Analytics, Trader's Cabinet. Each card: icon, title, description. Animate in on scroll. Hover state elevates card with border highlight.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-b2core-traders-room.png)

---

**Task-27: B2CORE Page**
**Section-3: Platform Screenshots / Dashboard Preview**
**Task Title**: Build Interactive Dashboard Screenshot Carousel
**Description**: Full-width or contained lightbox-capable screenshot gallery showing B2CORE dashboard views (admin panel, client cabinet, reports). Implement a tabbed or thumbnail-strip carousel. Clicking a thumbnail opens a fullscreen lightbox with zoom capability.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-b2core-traders-room.png)

---

**Task-28: B2CORE Page**
**Section-4: Integrations List**
**Task Title**: Build Third-Party Integrations Logo Wall
**Description**: Grid of integration partner logos (payment gateways, trading platforms, KYC providers, wallets). Logos in monochrome with color on hover. Section heading "Integrations" with brief intro text. Data-driven from CMS — support adding/removing logos without code changes.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-b2core-traders-room.png)

---

**Task-29: B2CORE Page**
**Section-5: CTA / Lead Form**
**Task Title**: Build B2CORE Page Bottom Lead Form
**Description**: Standard bottom CTA section with email capture form. Headline "Ready to get started with B2CORE?", email input, submit button. Same reusable form component pattern. Success/error inline feedback.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-b2core-traders-room.png)

---

**Task-30: Copy & Social Trading Page (`/products/copy-trading-platform/`)**
**Section-1: Hero – Copy & Social Trading Software**
**Task Title**: Build Copy Trading Platform Hero
**Description**: Hero section with headline "Copy & Social Trading Software for Brokers", animated dashboard/chart visual, and CTAs. Highlight key value props (follower/strategy provider model, real-time copy, multi-platform). Sticky secondary nav.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-copy-trading-platform.png)

---

**Task-31: Copy Trading Page**
**Section-2: How It Works / Flow Diagram**
**Task Title**: Build Copy Trading Workflow Diagram Section
**Description**: Visual step-by-step flow diagram showing the copy trading process: Strategy Provider creates strategy → Followers subscribe → Trades auto-copied → P&L distributed. Use numbered steps with connecting arrows. Animated on scroll entry. Mobile collapses to vertical stepper.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-copy-trading-platform.png)

---

**Task-32: Copy Trading Page**
**Section-3: Features & Benefits Grid**
**Task Title**: Build Feature Cards Grid for Copy Trading Platform
**Description**: 3–4 column icon+text grid listing features: real-time trade copying, risk management tools, performance analytics, customizable commissions, multi-broker support, mobile app. Standard icon-card component reuse from other product pages. Staggered scroll animation.
![Page Screenshot](https://pub-51c3a7dccc2448f792c2fb1bacf8e05d.r2.dev/pm-agent/screenshots/1782328164/products-copy-trading-platform.png)

---

**Task-33: Copy Trading Page**
**Section-4: Platform Screenshots**
**Task Title**: Build Copy