# WESLEY GUIRRA
Phone: +55 11 99912-0747
E-mail: wesleeycosta7@gmail.com
Region/City: São Paulo - SP, Brazil
GitHub: https://github.com/wesguirra
LinkedIn: https://linkedin.com/in/wesleyguirra
Notice period: 14 days

## Summary
Senior React/Fullstack engineer with 10+ years shipping web and mobile products. Most recently I built and maintained a Next.js SDK running on Belk.com (US department store, ~13M monthly visits, $429M in 2024 online sales). After that contract wrapped I built Revund, a multi-LLM AI code review SaaS, end-to-end and solo — Go orchestrator, Next.js dashboard, ~60% drop in per-review cost via a provider-fallback chain. I'm strongest in `React`, `Next.js`, `TypeScript`, and `Node.js`, comfortable in `Go`, and have shipped production mobile in `React Native` and `Flutter`. I care about the parts that decide whether software actually works in production: caching, performance, infra, and the boring contracts between systems.

## Professional Background

### Fullstack Developer at BILDIT (2023/10 ~ 2026/05) *Contractor*
---
BILDIT is a banner management and live-editing CMS for ecommerce. I worked across the whole stack — the React CMS, the Firebase Functions backend, the published Next.js SDK that ecommerce sites install, and a custom template parser. The flagship customer was Belk.com (~13M monthly visits, $429.4M online sales in 2024).

- Built and maintained `@bildit-platform/nextjs`, the SDK Belk used to render CMS-managed banners on their storefront. Slot-based rendering, Shadow DOM for CSS isolation, client-side variant filtering for targeted content.
- Designed and shipped the SDK caching layer (`ETag`, CDN fallback, conditional strategies) so banner requests don't add latency to a 13M-visit storefront.
- Replaced the platform's hand-rolled string parser with a `Lezer`-based AST parser written in `TypeScript`. The new grammar eliminated a class of edge-case bugs (numbers in labels, boolean types, references) and made the parser extensible enough to ship new template features without rewriting it each time.
- Restructured the parser into discrete modules (parse-tree, parse-expressions, parse-groups, transform-expressions, literals) with real test coverage, and added an extensible serializer system so consumers can plug in custom type transformations without forking the core.
- Backend work on `Firebase Functions` (`Fastify` + Firebase Realtime Database): CVE patches, cache API improvements, multi-banner-per-slot support to unblock customer feature requests.

### Senior React Developer at Big Human (2022/06 ~ 2022/09) *Contractor*
---
Front-end and mobile work for a NYC product agency — architectural input on new builds, feature work and bugfixes on a wellness app, plus a Shopify project.

- Shipped an `SSR/SSG` `Next.js` site backed by `Contentful` over GraphQL, plus a `Gatsby` site with a headless CMS.
- Built features for a wellness mobile app in `React Native`.
- Shopify theme fixes and site infrastructure on `Netlify`.

### Senior Fullstack Developer at Funding Circle UK (2021/12 ~ 2022/05) *Contractor*
---
Worked on the credit APIs at one of the UK's largest SMB lending platforms — `Ruby on Rails` and `Clojure`. Investigated bugs, pushed XSS fixes on the front-end, and built features end-to-end.

- Migrated CI/CD off `CircleCI` onto `DroneCI` for the credit team.
- Shipped features in `Ruby on Rails`, business rules in `Clojure`, and implemented financial workflows end-to-end.
- Built features for an HR-focused web app with performance as a constraint.
- Ran a TDD/unit-testing onboarding session for interns joining the team.

### Senior Fullstack Developer at Clevertech (2021/06 ~ 2021/12)
---
- Shipped an `SSR/SSG` site integrated with `Contentful`, with SEO and page-speed work.
- Performance tuning on a `WordPress` site.
- Wrote a `Python` crawler to migrate structured data out of `WordPress` into a new CMS.

### Senior Developer / Tech Lead at OSBR (2019/11 ~ 2021/06)
---
Tech Lead for the engineering org. Owned production and non-production environments on `Azure`, ran SCRUM with 2 devs + designer + QA, helped land the DevOps shift. Set up CI/CD on `GoCD` and `Azure DevOps` for mobile, web, and APIs.

- Took over performance and SEO for **Ticket/Edenred's WordPress site (5M+ monthly visits)** — one of the largest benefits providers in Brazil and France. Page-speed and ranking improvements across the site.
- Designed and built financial APIs and `Flutter` mobile apps for selling gift cards through Android card machines.
- Defined `KPIs` for the technology side, wrote the SCM plan for the company's projects, ran code reviews and architecture decisions.

### Fullstack Engineer at Platform Builders (2018/10 ~ 2019/11)
---
Hybrid mobile (`React Native` with Redux/MobX) and `React` web apps for large Brazilian retailers — Hotel Jatiuca, Iguatemi Shopping, Pernambucanas. Also touched `Java`/`Spring` back-end work and brought CI/CD + Twelve-Factor habits to the team.

### Earlier roles (2016 ~ 2018)
---
- **Netbiis** (2018) — Front-end engineer, `AngularJS` for Engel & Voelkers and a `React` + `Socket.io` chatbot for Rede Globo.
- **4Linux** (2016–2017) — PHP/Drupal/Symfony work on the company CRM and website. Later taught the company's "Web Development with PHP" course.

## Side Projects

### Revund — AI Code Review SaaS
**Live at [revund.dev](https://revund.dev) · solo-built · closed source**
Multi-pass PR review (security, performance, architecture, style) that explains *why* each finding matters. Integrates with GitHub, GitLab (cloud + self-hosted), and Bitbucket.

- Stack: `Go` orchestrator + API + bot, `Next.js`/`TypeScript` dashboard and marketing site, `Node.js` + `ts-morph` sidecar for TS type-context, Postgres via `ent`, Supabase, `Stripe` billing, AWS Lightsail Container Service.
- **N-way provider chain with cost-tiered fallback** — each review pass has its own ordered chain (style → DeepSeek → Gemini → OpenAI → Anthropic; security → Anthropic → OpenAI). On 5xx/429/network errors the orchestrator falls through transparently while preserving the same finding schema across four wire formats (Anthropic prompt caching, OpenAI tool-calling, Gemini's `functionCall` array shape, DeepSeek on the OpenAI API). With prompt caching and a Haiku-default style pass, **average per-review cost dropped ~60% with no quality regression on the eval set**.
- Multi-tenant SaaS, paying-customer-ready: Stripe checkout + portal + webhooks wired, plan entitlements enforced.

### GRYM — Fitness app with real-time group training
**[grym.fit](https://grym.fit) · MVP in development**
Fitness app with AI-generated workouts, session tracking, social features, PT tools, and a B2B gym retention dashboard.

- Stack: `React Native`, `Next.js`, Supabase, Redis (WebSocket pub/sub), OpenAI/Anthropic for workout generation and AI coaching.
- Real-time group training sessions ("Pacts") — app coordinates workout rotation between two people over WebSocket, advancing screens automatically as each person finishes their set.
- B2B churn prediction engine scoring gym members by cancellation risk based on actual training behavior (frequency, intensity, drop-off patterns) rather than door-swipe heuristics.

### Balcão — Restaurant SaaS
**Live commercial side project · paying tenants in production**
Multi-tenant SaaS for Brazilian restaurants — customer ordering PWA, admin dashboard, POS with cash sessions, waiter app, and kitchen display, all tenant-scoped.

- Stack: `Next.js 14` (App Router), `TypeScript`, `Prisma`, Supabase, `Stripe` Billing, Tailwind, Redux Toolkit, PWA. Monorepo (npm workspaces) with a shared `@balcao/tenancy` package.
- One Next.js deployment serves every tenant: each route lives under `/[tenant]`, with a `resolve.ts` layer per API surface isolating data, settings, fiscal config, and even PWA manifest/icons per restaurant.
- AI-assisted onboarding (`ai/parse-menu`, `ai/import-products`, `ai/generate-product-copy`) turns a photo or PDF menu into a populated, copywritten catalog — removing the biggest friction point in restaurant SaaS onboarding.
- Integrations: iFood, Food99, WhatsApp (embedded signup), Pix, Brazilian fiscal docs, Stripe Billing with tiered plans (KDS gated by plan).

## Skills

**Front-end:** React, Next.js (App Router, SSR/SSG), TypeScript, GraphQL, Tailwind, Redux/Redux Toolkit, MobX. Earlier: Gatsby, Vue, Angular, AngularJS.

**Mobile:** React Native, Flutter. Some Swift and Kotlin for native work.

**Back-end:** Node.js, Fastify, Firebase Functions, Go, Ruby on Rails, PHP/Laravel, Clojure (business rules), Java/Spring (earlier).

**Infra & DevOps:** Docker, AWS Lightsail, Azure, Firebase, GoCD, Azure DevOps, CircleCI, DroneCI, Fastlane, Netlify, Vercel.

**Data:** PostgreSQL, MySQL, Supabase, dbt, Metabase, SQL.

**Design tooling:** Figma, Adobe Illustrator, Adobe Photoshop (UI/UX background).

## Education

**Pontifícia Universidade Católica do Rio Grande do Sul** — MBA in Business Technology: AI, Data Science and Big Data (2023)

**ENIAC** — Superior Analysis and System Development (2017)

## Certifications & Notable Specializations
- CertiProf — SCRUM Foundation Professional
- HackerRank — React Basic
- AWS IoT Foundation: Telemetry
- 4Linux — Agile Infrastructure: DevOps with Docker, Git, Jenkins, Puppet, Ansible
- 4Linux — Web Development with PHP (later taught the course in 2017)

## Articles (in Portuguese, all written pre-LLM era — 2018–2019)
- [Animated Forms in React-Native using SVG and Animated API](https://medium.com/fabmvp/criando-formas-animadas-no-react-native-usando-svg-e-animated-api-2b87c7a3b31c)
- [Dynamic List Fields in ReactJS](https://medium.com/reactbrasil/criando-lista-din%C3%A2mica-utilizando-reactjs-38f5faf65431)
- [Camera Masks in React-Native using SVG](https://medium.com/reactbrasil/criando-mascara-sobre-a-c%C3%A2mera-no-react-native-usando-svg-8353677a85c4)
- [Animated Progress Bar in React-Native](https://medium.com/reactbrasil/criando-barra-de-progresso-horizontal-animada-usando-a-animated-api-no-react-native-7cc8d4d22c79)
- [Developing a Flutter Plugin](https://medium.com/flutter-comunidade-br/desenvolvendo-um-plugin-para-flutter-9c81b683189)