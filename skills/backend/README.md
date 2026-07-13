# Backend Skills & Resources

Curated, verified open-source repositories and Claude Skills for building backend services — Node.js/Python web frameworks, ORMs/databases, authentication, real-time communication, file uploads, and GraphQL. Use this list when scaffolding an API, choosing an auth strategy, or wiring up real-time features.

## Best Repositories

### [Express](https://github.com/expressjs/express)
- **Stars:** ~69,366 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-12

Fast, unopinionated, minimalist web framework for Node.js. The most widely used HTTP framework in the Node ecosystem and the foundation many other frameworks build on.

**Why it's included:** the default choice for REST APIs in Node.js; huge middleware ecosystem, simple mental model, works with almost every auth/upload/websocket library below.

**Installation:**
```bash
npm install express
```

**Usage example:**
```js
import express from 'express'

const app = express()

app.get('/', (req, res) => {
  res.send('Hello World')
})

app.listen(3000, () => {
  console.log('Server is running on http://localhost:3000')
})
```

---

### [Fastify](https://github.com/fastify/fastify)
- **Stars:** ~36,799 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-12

A fast, low-overhead Node.js web framework with schema-based validation, a powerful plugin architecture, and first-class TypeScript support.

**Why it's included:** a modern, higher-performance alternative to Express for REST API design, with built-in JSON schema validation — good for teams that want more structure out of the box.

**Installation:**
```bash
npm install fastify
```

**Usage example:**
```js
import Fastify from 'fastify'

const fastify = Fastify({ logger: true })

fastify.get('/', async (request, reply) => {
  return { hello: 'world' }
})

fastify.listen({ port: 3000 }, (err) => {
  if (err) throw err
})
```

---

### [Django](https://github.com/django/django)
- **Stars:** ~88,181 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, last push 2026-07-13

A batteries-included Python web framework with a built-in ORM (supports PostgreSQL, SQLite, MySQL and more), admin panel, auth system, and REST-friendly routing.

**Why it's included:** the standard choice for full-featured Python backends where you want an ORM, admin UI, and auth included rather than assembled from separate packages.

**Installation:**
```bash
pip install django
django-admin startproject mysite
```

**Usage example:**
```python
# mysite/urls.py
from django.http import HttpResponse
from django.urls import path

def hello(request):
    return HttpResponse("Hello, World!")

urlpatterns = [path("", hello)]
```

---

### [Flask](https://github.com/pallets/flask)
- **Stars:** ~71,916 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, last push 2026-06-10

A lightweight Python micro-framework that gives you routing and templating and lets you add exactly the extensions you need (SQLAlchemy, auth, etc).

**Why it's included:** the go-to minimal Python framework for small services and APIs, or when you want full control over architecture instead of Django's conventions.

**Installation:**
```bash
pip install flask
```

**Usage example:**
```python
# save this as app.py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, World!"
```
```bash
flask run
```

---

### [Prisma](https://github.com/prisma/prisma)
- **Stars:** ~47,335 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, last push 2026-07-10

A next-generation, type-safe ORM for Node.js and TypeScript supporting PostgreSQL, MySQL, MariaDB, SQL Server, SQLite, MongoDB, and CockroachDB from one client API.

**Why it's included:** covers PostgreSQL/SQLite/MongoDB data access in a single, well-documented tool with auto-generated types and migrations — reduces hand-written SQL/boilerplate.

**Installation:**
```bash
npm install prisma --save-dev
npm install @prisma/client
```

**Usage example:**
```ts
import { PrismaClient } from './generated/client'

const prisma = new PrismaClient()
const allUsers = await prisma.user.findMany({
  include: { posts: true },
})
```

---

### [Auth.js (next-auth)](https://github.com/nextauthjs/next-auth)
- **Stars:** ~28,303 (as of 2026-07-13)
- **License:** ISC
- **Last updated:** actively maintained, last push 2026-06-12

Authentication for the web, built on standard Web APIs and working across Next.js, SvelteKit, Express, Remix, and more. Supports OAuth, email/passwordless, and credentials-based sign-in.

**Why it's included:** the most common drop-in authentication solution for JS/TS full-stack apps, with first-party framework adapters and session/JWT handling done for you.

**Installation:**
```bash
npm install next-auth
```

**Usage example:**
```ts
// auth.ts
import NextAuth from "next-auth"
import GitHub from "next-auth/providers/github"

export const { handlers, auth } = NextAuth({
  providers: [GitHub],
})
```

---

### [Socket.IO](https://github.com/socketio/socket.io)
- **Stars:** ~63,296 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-06-25

A bidirectional, low-latency event-based communication library between browser/mobile clients and Node.js servers, with automatic reconnection and fallback transports.

**Why it's included:** the most mature and widely deployed WebSocket abstraction for real-time features (chat, notifications, live dashboards) in Node.js backends.

**Installation:**
```bash
npm install socket.io
```

**Usage example:**
```js
// server
import { Server } from 'socket.io'
const io = new Server(3000)

io.on('connection', (socket) => {
  socket.on('chat message', (msg) => {
    io.emit('chat message', msg)
  })
})
```
```js
// client
import { io } from 'socket.io-client'
const socket = io('http://localhost:3000')
socket.emit('chat message', 'hello')
```

---

### [Multer](https://github.com/expressjs/multer)
- **Stars:** ~12,063 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-01

Node.js middleware for handling `multipart/form-data`, used for uploading files in Express (and Express-compatible) applications.

**Why it's included:** the standard way to accept file uploads (avatars, documents, media) in a Node/Express REST API without building multipart parsing yourself.

**Installation:**
```bash
npm install multer
```

**Usage example:**
```js
import express from 'express'
import multer from 'multer'
const upload = multer({ dest: 'uploads/' })
const app = express()

app.post('/profile', upload.single('avatar'), (req, res) => {
  // req.file contains the uploaded avatar
  res.send('Uploaded')
})
```

---

### [Apollo Server](https://github.com/apollographql/apollo-server)
- **Stars:** ~13,943 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-12

A spec-compliant, production-ready JavaScript GraphQL server that works standalone or on top of Express, Koa, Hapi, and more.

**Why it's included:** the most established GraphQL server implementation in the Node ecosystem, for teams that want typed, schema-first APIs instead of (or alongside) REST.

**Installation:**
```bash
npm install @apollo/server graphql
```

**Usage example:**
```js
import { ApolloServer } from '@apollo/server'
import { startStandaloneServer } from '@apollo/server/standalone'

const typeDefs = `type Query { hello: String }`
const resolvers = { Query: { hello: () => 'Hello world!' } }

const server = new ApolloServer({ typeDefs, resolvers })
const { url } = await startStandaloneServer(server, { listen: { port: 4000 } })
console.log(`Server ready at ${url}`)
```

---

### [Convex Skills](https://github.com/waynesutton/convexskills)
- **Stars:** ~399 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, last push 2026-02-06

An AI-agent-consumable skills package (Agent Skills open format) that teaches Claude and other coding agents production-ready backend patterns for Convex — queries, mutations, cron jobs, webhooks, migrations, and file uploads.

**Why it's included:** a real, actively-used "Claude Skill" specifically for backend development, filling the request for AI-assistant-oriented backend skill packages rather than just plain libraries.

**Installation:**
```bash
npm install -g @waynesutton/convex-skills
convex-skills install-all
```

**Usage example:**
```text
"Help me set up file uploads in Convex"
"Create a cron job to clean up expired sessions"
"Add a webhook endpoint for Stripe"
```

## Notes
- `jaredhanson/passport` (the classic Node.js auth middleware, MIT, ~23.5k stars) was considered but excluded from the main list because its last push was 2024-08-16 — nearly two years stale as of this write-up — so Auth.js was preferred as the more actively maintained authentication option. Passport is still widely deployed and safe to use if you need its specific OAuth/SAML strategy ecosystem.
- Prisma's single client already covers PostgreSQL, MySQL, SQLite, and MongoDB, so no separate MongoDB driver/ODM was added; add `mongoose` separately if you need MongoDB-only, non-Prisma tooling.
- Star counts and license data were pulled live via the GitHub API on 2026-07-13 and reflect that date only.
- "Claude Skills" packages for backend (like Convex Skills) are a new and fast-moving category — re-verify star count/activity before relying on them long-term.

## License Summary
| Repository | License |
|---|---|
| expressjs/express | MIT |
| fastify/fastify | MIT |
| django/django | BSD-3-Clause |
| pallets/flask | BSD-3-Clause |
| prisma/prisma | Apache-2.0 |
| nextauthjs/next-auth | ISC |
| socketio/socket.io | MIT |
| expressjs/multer | MIT |
| apollographql/apollo-server | MIT |
| waynesutton/convexskills | Apache-2.0 |
