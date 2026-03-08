Read ALL of the following files that exist in this project directory: REPO_MAP.md, TECH_STACK.md, ENV_CONFIG_MAP.md, REQUEST_FLOW_NOTES.md, DATA_ARCHITECTURE.md, UI_COMPONENT_MAP.md, DEPLOYMENT_GUIDE.md, INTEGRATIONS.md, ONBOARDING.md, ARCHITECTURE_DECISIONS.md. Also read all .mermaid files.

You are going to produce a series of deep-dive documents that will be consumed as audio via text-to-speech during a 3-hour drive. The listener is a senior solutions architect / software engineer who is encountering this codebase for the first time and wants to deeply understand the system by the time they arrive.

AUDIO-FIRST WRITING RULES (follow these strictly):
- Write in a conversational, narrative tone — like a senior tech lead walking a new architect through the system over coffee
- NO bullet points, NO numbered lists, NO tables, NO markdown formatting, NO headers within sections — just flowing prose paragraphs. Headers only for episode/chapter titles.
- NO code snippets, NO file paths in isolation — instead say "the user model, which lives in the data layer alongside the other Prisma schemas" or "the authentication middleware that sits in the API gateway package"
- Spell out all abbreviations on first use: "ORM, which stands for Object Relational Mapper" and "the CI CD pipeline, meaning continuous integration and continuous deployment"
- When referencing architecture patterns, explain them — don't assume the listener remembers every Gang of Four pattern while driving
- Use verbal transitions between topics: "Now that we understand how the data is stored, let's follow a request from the moment a user clicks a button..."
- Use analogies and mental models liberally — "Think of this like a mail room that sorts incoming requests before they reach the right department"
- Periodically recap: "So to recap what we've covered so far..." every 10-15 minutes of content (roughly every 1500-2000 words)
- Avoid saying "as we saw in the diagram" or "refer to the table above" — there are no visuals, only audio
- When describing relationships between components, be spatially explicit: "Service A calls Service B, which then writes to the database and fires off an event that Service C picks up asynchronously"

Produce the following files. Each should be 3500-5000 words (roughly 25-35 minutes of listening at natural speech pace). Together they should cover approximately 3 hours.

EPISODE 1: `DRIVE_01_THE_BIG_PICTURE.md`
The 30,000 foot view. What does this system do, who uses it, what problem does it solve? Walk through the monorepo structure as if describing a building — "when you walk in the front door, you're in the main Next.js application, which is the primary thing users interact with. Down the hall, there's the API service that handles all the heavy lifting..." Cover the major packages, how they relate to each other, and why the team likely chose a monorepo structure. End with a mental model the listener can hold in their head for the rest of the drive — "the simplest way to think about this system is..."

EPISODE 2: `DRIVE_02_THE_TECH_STACK_STORY.md`
Go through every significant technology in the stack, but tell the STORY of why each was likely chosen. Don't just say "we use Prisma" — say "for talking to the database, the team chose Prisma, which is an ORM that lets you define your data models in a schema file and then generates TypeScript types from that schema. The interesting thing about this choice is..." Group technologies by the problem they solve, not by category. Cover the tradeoffs — what did they gain and what did they give up with each choice? Where are there redundancies or tensions in the stack?

EPISODE 3: `DRIVE_03_FOLLOWING_A_REQUEST.md`
The most important episode. Pick the single most representative user action in the system — something that touches authentication, the API, business logic, the database, and ideally some async processing. Then narrate the ENTIRE journey of that request, step by step, as if you're a packet of data traveling through the system. "It starts when the user clicks the submit button. The React component captures the form data and passes it to a custom hook, which calls... The request leaves the browser and hits... The first thing that happens server-side is..." Go deep. Mention specific middleware, validation steps, database queries, error handling. When you reach a fork (like an async job being queued), follow both paths. This episode should make the listener feel like they've personally traced a debugger through the system.

EPISODE 4: `DRIVE_04_THE_DATA_LAYER.md`
Everything about how data is stored, modeled, and accessed. Start with the domain model — what are the core entities and how do they relate to each other? Describe them as characters in a story: "The User is the central character — almost everything in the system relates back to a User. A User can have many Projects, and each Project contains..." Then cover the database engine, how migrations work, any caching strategies, file storage, search indexes, vector databases. Talk about the read and write patterns — is this a read-heavy system? Write-heavy? Are there any clever optimizations or concerning patterns?

EPISODE 5: `DRIVE_05_THE_FRONTEND_EXPERIENCE.md`
Walk through the frontend as if you're a user navigating the application for the first time, but with X-ray vision that lets you see the code behind every page. "When you first land on the app, you hit the landing page, which is actually a statically generated page for fast loading. If you're not logged in, you see... The moment you click Sign In, the auth flow kicks in using..." Cover routing, state management, data fetching patterns, shared components, and any non-trivial UI behaviors like real-time updates or optimistic rendering. Explain the architectural decisions behind the frontend — why server components here but client components there?

EPISODE 6: `DRIVE_06_INFRASTRUCTURE_AND_DEPLOYMENT.md`
How does this thing actually run in production? Walk through the deployment architecture as if giving a tour of a data center. "The frontend is deployed to Vercel, which means it's running on edge servers distributed globally. When a user in Tokyo makes a request, it hits the nearest Vercel edge node, which..." Cover the CI/CD pipeline step by step, how environments are managed, where secrets live, and how you'd deploy a change from a pull request all the way to production. Include what happens when things go wrong — monitoring, alerting, rollback strategies.

EPISODE 7: `DRIVE_07_RISKS_DECISIONS_AND_WHAT_I_WOULD_CHANGE.md`
The architect's opinion piece. Now that the listener understands the entire system, give them the senior architect's honest assessment. What are the smartest decisions in this codebase and why? What patterns concern you? Where is there technical debt accumulating? What would break first if the user base grew 10x? What would you change if you were leading the team? What are the open questions you'd want to ask the original developers? End with a prioritized list (described verbally, not as a bullet list) of the three things you'd investigate first on Monday morning.

IMPORTANT: Each episode should begin with a brief "Previously on..." recap (2-3 sentences) of what was covered in earlier episodes, so the listener can re-orient if their attention drifted. Each episode should end with a teaser for the next one: "In the next episode, we'll dig into..."

IMPORTANT: The writing should be dense with actual specifics from this codebase — real package names, real technology choices, real architectural patterns you observed. This is NOT a generic software architecture lecture. Every sentence should be grounded in what you actually found in the code.