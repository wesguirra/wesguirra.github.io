# WESLEY GUIRRA
Phone: +55 11 99912-0747
E-mail: wesleeycosta7@gmail.com
Region/City: São Paulo - SP, Brazil
Github: https://github.com/wesguirra
LinkedIn: https://linkedin.com/in/wesleyguirra
Last salary: **USD 25/h**
Expected gross salary: Open to offers
Availability: Immediate

```
Silent Reading Time of this Resume: ~5 mins
Words: ~1200
```

## Summary
I'm a Senior React/Fullstack engineer with 10+ years shipping web and mobile products — ecommerce, fintech, wellness, and the SaaS I'm building right now on the side. My day-to-day is `React`, `Next.js`, `TypeScript`, and `Node.js`, but I also reach for `Go` and `React Native`/`Flutter` when the problem calls for it. I like the messy parts of the job: replacing fragile string parsers with proper grammars, getting an SDK to behave nicely inside someone else's site, making LLM calls cheap and reliable in production. I write articles in Portuguese for the local dev community and I learn fastest by building things and breaking them.

## Side Projects

### Revund — AI Code Review SaaS
**Live at [revund.dev](https://revund.dev) · solo-built · closed source**
Multi-pass PR review (security, performance, architecture, style) that explains *why* each finding matters, plugged into GitHub, GitLab (cloud + self-hosted), and Bitbucket. Built end-to-end on my own.

- `Go` orchestrator + API + bot, `Next.js`/`TypeScript` dashboard and marketing site, `Node.js` + `ts-morph` sidecar for TS type-context, Postgres via `ent` + Supabase, `Stripe` billing, Lightsail Container Service.
- The thing I'm proudest of is the N-way provider chain. Each review pass has its own ordered fallback (style goes DeepSeek → Gemini → OpenAI → Anthropic; security goes Anthropic → OpenAI). On 5xx/429/network errors the orchestrator falls through transparently and keeps the same finding schema across four very different wire formats — Anthropic prompt caching, OpenAI tool-calling, Gemini's `functionCall` array shape, DeepSeek riding the OpenAI API. With system-prompt caching and a Haiku-default style pass, average review cost dropped ~60% with no quality regression on my eval set. Any single provider going down stops mattering.
- Multi-tenant, paying-customer-ready: Stripe checkout + portal + webhooks wired, plan entitlements enforced.

### GRYM — Fitness app with real-time group training
**[grym.fit](https://grym.fit) · MVP in development**
Fitness app with AI-generated workouts, session tracking, social features, tools for personal trainers, and a B2B gym retention dashboard.

- `React Native`, `Next.js`, Supabase, Redis (WebSocket pub/sub), LLM integration for workout generation and AI coaching.
- Built real-time group training sessions ("Pacts") where the app coordinates workout rotation between two people over WebSocket — one person finishes their set, the other's screen advances automatically.
- On the B2B side, a churn prediction engine that scores gym members by cancellation risk based on actual training behavior (frequency, intensity, drop-off patterns) rather than the usual door-swipe heuristic.

### Balcão — Restaurant SaaS
**Live commercial side project · paying tenants in production**
Multi-tenant SaaS for Brazilian restaurants — customer ordering PWA, admin dashboard, POS, waiter app, and kitchen display, all under one tenant-scoped platform.

- `Next.js 14` (App Router), `TypeScript`, `Prisma`, Supabase, `Stripe`, Tailwind, Redux Toolkit, PWA. Monorepo (npm workspaces) with a shared `@balcao/tenancy` package.
- One Next.js app serves every tenant: each route lives under `/[tenant]`, and a `resolve.ts` layer per API surface keeps data, settings, fiscal config, and even the PWA manifest/icons isolated per restaurant.
- AI-assisted onboarding turned out to be the unlock — `ai/parse-menu`, `ai/import-products`, and `ai/generate-product-copy` let a restaurant point at a photo or PDF of their menu and end up with a populated, copywritten catalog. Onboarding friction is the #1 reason restaurant SaaS dies and this killed most of it.
- Integrations with iFood, Food99, WhatsApp (embedded signup), Pix, Brazilian fiscal docs, and Stripe Billing with tiered plans (KDS gated by plan).

## Professional Background

### Fullstack Developer at BILDIT (2023/10 ~ 2026/04) *Contractor*
---
BILDIT is a banner management and live-editing CMS for ecommerce. I've been working across the whole stack — the React CMS, the Firebase Functions backend, the Next.js SDK that ecommerce sites install to render banners, and a custom template parser. I also helped shape the monorepo and the developer experience for the npm packages we ship publicly.

#### Things I'm proud of
- Replaced the manual string parsing of banner template expressions with a proper `Lezer`-based AST parser. The old approach broke on edge cases like numbers in labels, boolean types, and references — the new grammar handles them cleanly and is way easier to extend.
- Migrated the parser to `TypeScript` and broke it into discrete modules (parse-tree, parse-expressions, parse-groups, transform-expressions, literals) with real test coverage instead of vibes.
- Designed an extensible serializer system so consumers can plug in custom type transformations without forking the core library.
- Built and maintain `@bildit-platform/nextjs`, the SDK ecommerce sites use to render CMS-managed banners. Slot-based rendering, Shadow DOM for CSS isolation (so our styles don't fight the host site), client-side variant filtering for targeted content.
- Layered on a real caching system — `ETag` support, CDN fallback, conditional strategies — which dropped API load and shaved meaningful time off page loads for sites consuming the SDK.
- Backend work in `Firebase Functions` with `Fastify` and Firebase Realtime Database.
- Steady stream of unsexy but important wins: CVE patches, cache API improvements, multi-banner-per-slot support to unblock client features.

### Senior React Developer at Big Human (2022/06 ~ 2022/09) *Contractor*
---
Front-end and mobile work — architectural input on new builds, feature work and bugfixes on a wellness app, plus a Shopify project on the side.

- Shipped an `SSR/SSG` `Next.js` site backed by `Contentful` over GraphQL.
- Built features for a wellness mobile app in `React Native`.
- Shopify theme fixes when needed.
- Site infra on `Netlify`.
- Another `SSR/SSG` site on `Gatsby` with a headless CMS.

### Senior Fullstack Developer at Funding Circle UK (2021/12 ~ 2022/05) *Contractor*
---
Worked on the credit APIs (Ruby on Rails and Clojure), chased down bugs, and pushed through security improvements on the front-end — mostly XSS-related.

- Migrated CI/CD off `CircleCI` onto `DroneCI`.
- Investigated bugs deep enough that I had to actually understand the credit business — which paid off.
- Built features for an HR-focused web app, with performance as a real constraint.
- Ran a TDD/unit-testing session for interns joining the team.
- Shipped features in `Ruby on Rails`, business rules in `Clojure`, and implemented financial workflows end-to-end.

### Senior Fullstack Developer at Clevertech (2021/06 ~ 2021/12)
---
- Shipped an `SSR/SSG` site integrated with `Contentful`.
- Pushed `SEO` improvements and chased page-speed wins.
- Performance tuning on a `WordPress` site.
- Wrote a `Python` crawler to migrate structured data out of `WordPress` into something less painful.
- Site infra on `Netlify`.

### Senior Developer / Tech Lead at OSBR (2019/11 ~ 2021/06)
---
Tech Lead for the engineering org — reviewing code, suggesting patterns, running SCRUM with two devs, a designer, and a QA. I owned production and non-production environments (mostly Azure) and helped land the DevOps shift. Plenty of greenfield work too: PoCs in Flutter, React, and headless CMS.

- Set up `CI/CD` for mobile, web, and API projects on `GoCD` and `Azure DevOps`.
- Built a credit card machine Android app in `Flutter`.
- Led the dev/QA team and defined `KPIs` for the technology side.
- Wrote the SCM plan for the company's projects.
- Maintained app infra on `Azure`.
- Took over performance and SEO for a `WordPress` site doing 5M+ monthly visits — Ticket/Edenred (one of the biggest benefits providers in Brazil and France). Faster pages, better rankings, less crying.
- Designed and built financial APIs and `Flutter` mobile apps for selling gift cards through Android card machines.

### Fullstack Engineer at Platform Builders (2018/10 ~ 2019/11)
---
Mostly hybrid mobile work in `React Native` (Redux, MobX) — apps that big retailers used to validate new business models. I carried CI/CD habits and Twelve-Factor thinking from those projects, and dipped into `Java`/`Spring` back-end when the work needed it.

- Content-driven `React` app for Hotel Jatiuca.
- The CMS web app powering it, also `React`.
- UI design + `React Native` app for mechanical car stores.
- Workflow approval app for Iguatemi Shopping in `React Native`.
- T-shirt customization web app for Pernambucanas in `React`.

### Front-end Engineer at Netbiis (2018/06 ~ 2018/10)
---
Front-end features, bugfixes, and architectural suggestions, mostly in `AngularJS`. Some `React` work too — including a chatbot built on `Socket.io`.

- `AngularJS` web app for Engel & Voelkers.
- `React` chatbot for Rede Globo.

### Fullstack Engineer at 4Linux (2016/02 ~ 2017/07)
---
PHP work on the company CRM and a Drupal site (SEO and performance focus), plus a stretch where I shared UI/UX duties with the marketing team — banner ads, web mockups, the works.

- Site work in `Drupal` + `Symfony`, SMACSS on the front-end.
- UI/UX prototyping.
- Ad creative in Photoshop, visual identity in Illustrator.
- Taught the company's "Web Development with `PHP`" course.
- Wrote the assessments used to hire visual designers (Illustrator, Photoshop, Premiere).
- Built video interview templates (lower thirds, intros).

## Skills

### Front-end & Architecture
React at scale is where I'm strongest. `React`, `Next.js`, `TypeScript` across multiple production platforms — SSR/SSG sites integrated with headless CMS (Contentful, Strapi), and a published Next.js SDK that external teams install in their own apps. I've worked with `Gatsby`, `VueJS`, `Angular`, and `AngularJS`, and `GraphQL` is in the toolbelt.

### Mobile
Production apps in both `React Native` and `Flutter` — wellness, workflow tools, financial apps running on Android card machines. Some early `Swift` and `Kotlin` for native work.

### Back-end & APIs
Mostly `Node.js` and `Firebase Functions` (with `Fastify`), plus solid time in `Ruby on Rails`, `PHP`, and `Laravel`. Lately I've been writing a lot of `Go` for Revund. I've also done business-rules work in `Clojure` and earlier-career `Java`/`Spring`.

### Infrastructure & DevOps
CI/CD pipelines on `GoCD`, `Azure DevOps`, `CircleCI`, `DroneCI`, and `Fastlane`. Cloud on `Azure`, `Firebase`, and AWS Lightsail. Comfortable with `Docker`, `PostgreSQL`, `MySQL`.

### Data & BI
`SQL`, `dbt`, and `Metabase` for BI dashboards and pipelines on `PostgreSQL` warehouses.

### Design
UI/UX background — `Figma`, `Adobe Illustrator`, `Adobe Photoshop`. Useful mostly because I can read what designers actually mean and bridge the gap when specs are loose.

## Education, Formation and Specializations

#### **Pontifícia Universidade Católica do Rio Grande do Sul**
MBA in Business Technology: AI, Data Science and Big Data, Information Technology (2023)

#### **ENIAC**
Superior Analysis and System Development (2017)
- API + web + mobile apps focused on the doctor/patient relationship.
- API + iOS app for finding medicines around Guarulhos - SP.

---

#### Specializations
- **AWS** IoT Foundation: Telemetry
- **University of Michigan** Inspiring and Motivating Individuals
- **University of Virginia** Digital Transformation
- **LinkedIn** Online Marketing Foundations
- **Fundação Bradesco** Structured System Analysis
- **4Linux** Web Development with PHP (I taught this course later in 2017)
- **4Linux** Agile Infrastructure: DevOps best practices using Docker, Git, Jenkins, Puppet, and Ansible
- **SENAI** Transversal Competence in Information and Communication Technologies

#### Certifications
- **CertiProf** SCRUM Foundation Professional
- **HackerRank** React Basic

## Pushed apps
- [Rota combustivel (Google Play)](https://play.google.com/store/apps/details?id=es.dgtalhero.rotacombustivel&pli=1)

## Articles
- [Creating Animated Forms in React-Native using SVG and Animated API (In Portuguese)](https://medium.com/fabmvp/criando-formas-animadas-no-react-native-usando-svg-e-animated-api-2b87c7a3b31c)
- [Creating Dynamic List fields using ReactJS (In Portuguese)](https://medium.com/reactbrasil/criando-lista-din%C3%A2mica-utilizando-reactjs-38f5faf65431)
- [Creating Mask Above Camera using React-Native and SVG (In Portuguese)](https://medium.com/reactbrasil/criando-mascara-sobre-a-c%C3%A2mera-no-react-native-usando-svg-8353677a85c4)
- [Creating Animated Horizontal Progress Bar using React-Native and Animated API (In Portuguese)](https://medium.com/reactbrasil/criando-barra-de-progresso-horizontal-animada-usando-a-animated-api-no-react-native-7cc8d4d22c79)
- [Developing a Flutter Plugin (In Portuguese)](https://medium.com/flutter-comunidade-br/desenvolvendo-um-plugin-para-flutter-9c81b683189)

This resume was written in Markdown by me, I used dillinger.io and it works like ✨magic✨ — hit me up if you want help writing your own.