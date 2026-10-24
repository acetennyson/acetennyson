<h1 align="center">Ado Daniel NJI</h1>

<p align="center"><strong>Engineering Secure, Automated &amp; Adaptable Systems</strong></p>

<p align="center">
  <a href="https://adodanielnj.vercel.app">Portfolio</a> ·
  <a href="https://www.linkedin.com/in/iamsupreme/">LinkedIn</a> ·
  <a href="https://dev.to/adodanieln">DEV</a> ·
  <a href="mailto:adodanieln@gmail.com">Email</a>
</p>

---

I'm a software developer in Cameroon. I work on backends, APIs, real-time systems and AI integrations, and what interests me most is the space between components: where the boundaries sit, what happens when a request is retried or two edits collide, and what someone else needs in order to build on top of what you made.

Most of my work is TypeScript with Next.js, Node and Postgres. Some of it lives in private repositories, so the descriptions below say what each project does and what I built, and link to code where it's public.

## Selected work

### Beta Gamer

[Site](https://bhetagamer.com) · [Docs](https://docs.bhetagamer.com) · [React SDK](https://www.npmjs.com/package/@beta-gamer/react) · [React Native SDK](https://www.npmjs.com/package/@beta-gamer/react-native)

Games-as-a-service: an app that wants multiplayer games calls an API instead of building game servers and matchmaking of its own.

Each partner is a tenant with isolated, rating-based matchmaking, so its players only meet each other. The partner's backend creates a session and gets back a short-lived token for the client SDK, and results return as signed webhooks. Matchmaking is group-first, so a 1v1 is a group of two rather than a special case. Besides the queue, a session can be a private room or a game against a bot, and a hosted mode lets the partner's backend assemble matches itself. Bots can be injected into live sessions with their logic driven entirely from outside. Ten games are playable, with React and React Native SDKs on npm.

### Task Manager API

[Code](https://github.com/acetennyson/global-tech-trial) · [Live playground](https://global-tech-trial.vercel.app)

A REST API I built as a skill assessment, so it's small, but I used it to work through the parts of an API that tend to get skipped. A retried create carries an `Idempotency-Key` and returns the original task instead of a duplicate. Updates carry a version number, and a stale one gets a `409` with the current task rather than overwriting someone's edit. Bulk writes are all-or-nothing in one transaction. Auth is JWT with hashed, single-use reset tokens, a forgot-password flow that doesn't reveal which emails are registered, and Postgres-backed rate limits. A `/api/sync` endpoint covers the server side of offline clients; no offline client exists yet. The README is open about its known limitations and lists what I'd change at scale, in priority order.

### JobHub

[Live](https://jobhub-psi.vercel.app)

A job board that scores listings against a candidate's skills, seniority and location, and shows why each one matched. Matching combines TF-IDF with cosine similarity and Jaro-Winkler string similarity, weighted across those three factors, so it goes beyond keyword overlap. Employers are reviewed before they can post, candidates get alerts for strong new matches, and API keys and webhooks let other platforms push listings in or pull them out.

### NightShift

[Code](https://github.com/acetennyson/global-freelancer-assistant) · [Demo](https://global-freelancer-assistant.vercel.app)

Client outreach for freelancers working across time zones. It reads clients from a Notion database, tracks each one's local time and availability window, drafts messages with AI using previously sent messages as context, and sends approved drafts when the window opens. A scheduled job checks every 15 minutes. The AI layer is multi-provider with key rotation, and an MCP server exposes three tools to Claude Desktop. Built for the Notion MCP Challenge.

### Also

- **Mbende Stay** ([mbendestay.com](https://mbendestay.com)): a property listing and rental platform for Cameroon. I contribute backend and product work.
- **SafeCircle**: a hackathon project in which guardian mobile apps and GPS tracker devices communicate over persistent WebSocket connections (Socket.IO), with real-time alerts, a community safe-zone feed and AI-assisted post classification. The apps are built with Capacitor.
- **Axir**: an AI assistant I'm building toward a workspace where organizations configure their own agents. The work so far is on tool execution and orchestration, a provider abstraction so models are swappable, task persistence, and a multi-tenant model so it isn't built around one user. It's in development.

## Tools

| Area | What I use |
| --- | --- |
| Languages | TypeScript, JavaScript, PHP |
| App and backend | Next.js, React, React Native, Capacitor, Node.js |
| APIs and real-time | REST, WebSockets / Socket.IO, HMAC webhooks, JWT, Zod |
| Data | PostgreSQL, Supabase, Redis (Upstash), Firebase, Prisma |
| AI and automation | MCP, Gemini / Claude / Groq APIs, Notion API |
| Infrastructure | Vercel, Docker, GitHub Actions |
| Payments | MTN MoMo, Orange Money, Tranzak, Stripe, PayPal |

## Get in touch

If you're reading one of the repos and have a question, or you'd have done something differently, I'd like to hear it. The Task Manager README lists its known limitations and what I'd tackle first; if you'd order them differently, I'd like to know why. Issues are open on the public repos, and email works too.

I also write about what I'm learning on [my site](https://adodanielnj.vercel.app/blog) and on [DEV](https://dev.to/adodanieln).
