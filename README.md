# 🏋️ Repwise

Repwise is a modern serverless SaaS platform built for personal trainers and their clients. It enables clients to discover trainers, purchase custom workout programs, stream high-quality video lessons via HLS, interact via real-time WebSocket chat, and book 1-on-1 WebRTC video coaching sessions. Trainers receive a comprehensive dashboard with revenue analytics, client management, lesson uploads, and flexible schedule settings.

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Architecture & Technical Documentation](#-architecture--technical-documentation)
- [Documentation Links (Techdocs)](#-documentation-links-techdocs)
- [Installation & Local Development](#-installation--local-development)
- [Deployment](#-deployment)
- [License](#-license)
- [Connect with me](#-connect-with-me)

---

## 🎯 Project Overview

**Repwise** bridges client engagement and trainer management through a scalable fullstack TypeScript architecture.

- **For Clients:** Search trainer profiles, purchase workout programs, watch adaptive HLS video lessons, participate in real-time chat with reactions and threads, and join low-latency 1-on-1 WebRTC live sessions.
- **For Trainers:** Analytics dashboard for tracking earnings, full client base management, media upload workflows for video lessons, and real-time appointment booking slot configuration.

---

## ✨ Key Features

- 📹 **Adaptive Video Streaming:** HLS video lesson delivery powered by ImageKit with dynamic bitrate selection.
- 💬 **Real-time Chat & WebRTC:** Feature-rich WebSocket chat (threads, reactions) and 1-on-1 WebRTC video calls using Stream.
- 📅 **Real-time Slot Booking:** Live schedule management and slot booking powered by Neon Realtime.
- 💳 **Stripe Marketplace Payments:** Integrated checkout flows with platform commission splitting.
- 🔐 **Better Auth Security:** Email/Password and Google OAuth authentication flows.
- 🛡️ **Automated Bug Fixing:** Error tracking via Sentry with autonomous PR diagnosis via Sentry Seer.

---

## 🛠️ Tech Stack

| Category                | Technology / Service                                             | Purpose                                                       |
| ----------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------- |
| **Runtime & Framework** | **Node.js + Next.js (App Router)**                               | Core Fullstack TypeScript application framework               |
| **Database**            | **Neon Postgres**                                                | Serverless cloud PostgreSQL database with Realtime engine     |
| **ORM & Migrations**    | **Drizzle ORM**                                                  | Type-safe database queries and migration management           |
| **Authentication**      | **Better Auth**                                                  | Client & server authentication (Email/Password, Google OAuth) |
| **Media Platform**      | **ImageKit (`imagekitio-next`)**                                 | Image transformations, uploads, and HLS video streaming       |
| **Chat & Video Calls**  | **Stream (`@stream-io/node-sdk`, `@stream-io/video-react-sdk`)** | WebRTC 1-on-1 video calls & WebSocket messaging               |
| **Payments**            | **Stripe**                                                       | Payment processing, customer billing, and marketplace splits  |
| **Monitoring & AI Fix** | **Sentry + Seer**                                                | Tracing, session replays, and automated PR bug fixes          |
| **Hosting & CI/CD**     | **Cloudways Velocity**                                           | Managed Node.js deployment automated from GitHub              |
| **AI Development**      | **Claude Code / Cursor**                                         | Autonomous coding agent driven by Claude 3.5 / 3.7 Sonnet     |
| **MCP Protocols**       | **Chrome, Sentry, Higsfield MCP**                                | Direct browser control, issue tracking, and asset generation  |

---

## 📐 Architecture & Technical Documentation

Repwise uses a serverless event-driven architecture designed for low-latency media delivery and high-concurrency real-time updates.

### Architectural Highlights

- **Media & HLS Delivery:** Client uploads are authenticated via server-side signatures (`app/api/upload-auth/route.ts`). Videos are processed by ImageKit for adaptive bitrate HLS delivery.
- **WebRTC & WebSocket Messaging:** Client video sessions and messaging tokens are signed on the server (`app/api/stream-token/route.ts`) and streamed directly via Stream infrastructure.
- **Relational Data & Realtime:** Neon Postgres handles persistent models (Users, Profiles, Programs, Lessons, Purchases, Slots) defined with Drizzle ORM, streaming real-time slot state changes directly to the UI.

For complete engineering breakdowns, consult the detailed architectural guide:

- 📄 <a href="./techdocs/Repwise%20Architecture,%20Services%20and%20AI%20Development%20Guide.pdf" target="_blank">Repwise Architecture, Services and AI Development Guide (PDF)</a>

### Architectural Diagrams

#### 1. Project Architecture and Service Interaction

![Project architecture and service interaction](<./techdocs/Project%20architecture%20and%20service%20interaction%20(Frontend,%20Backend,%20Neon,%20Stream,%20ImageKit)%20-%20repwise.jpg>)
_Figure 1: Complete architecture and integration topology between Next.js, Neon, ImageKit, Stream, Stripe, and Cloudways Velocity._

#### 2. AI-Driven SaaS Development Workflow

![AI-Driven SaaS Development Workflow](./techdocs/AI-Driven%20SaaS%20Development%20Workflow%20-%20repwise.jpg)
_Figure 2: 6-stage development lifecycle driven by AI agents from planning to production deployment._

#### 3. Database Structure and Relational Connections

![Database structure and relational connections](<./techdocs/Database%20structure%20and%20relational%20connections%20(Primary%20&%20Foreign%20Keys)(repwise).jpg>)
_Figure 3: Relational entity-relationship diagram for users, profiles, programs, lessons, purchases, and slots._

#### 4. Autonomous Error Resolution Flow with Sentry Seer

![Autonomous Error Resolution Flow with Sentry Seer](./techdocs/Autonomous%20Error%20Resolution%20Flow%20with%20Sentry%20Seer%20-%20repwise.jpg)
_Figure 4: Automated issue detection, diagnosis, and Pull Request resolution pipeline using Sentry and Seer._

---

## 📁 Documentation Links (Techdocs)

Access the raw assets and technical documents in the repository:

- 📁 [**/techdocs Folder**](./techdocs)

### PDF Documents

- 📄 <a href="./techdocs/Repwise%20Architecture,%20Services%20and%20AI%20Development%20Guide.pdf" target="_blank">Repwise Architecture, Services and AI Development Guide.pdf</a>

### Visual Diagrams & Images

- 🖼️ [AI-Driven SaaS Development Workflow - repwise.jpg](./techdocs/AI-Driven%20SaaS%20Development%20Workflow%20-%20repwise.jpg)
- 🖼️ [Autonomous Error Resolution Flow with Sentry Seer - repwise.jpg](./techdocs/Autonomous%20Error%20Resolution%20Flow%20with%20Sentry%20Seer%20-%20repwise.jpg)
- 🖼️ [Database structure and relational connections (Primary & Foreign Keys)(repwise).jpg](<./techdocs/Database%20structure%20and%20relational%20connections%20(Primary%20&%20Foreign%20Keys)(repwise).jpg>)
- 🖼️ [Project architecture and service interaction (Frontend, Backend, Neon, Stream, ImageKit) - repwise.jpg](<./techdocs/Project%20architecture%20and%20service%20interaction%20(Frontend,%20Backend,%20Neon,%20Stream,%20ImageKit)%20-%20repwise.jpg>)

### Markdown Documents

- 📄 [repwise.md](./techdocs/repwise.md)

---

## 🚀 Installation & Local Development

### Prerequisites

- **Node.js:** `>=18.x`
- **Package Manager:** `npm` / `yarn` / `pnpm`
- **Database:** Neon Postgres connection string

### Step-by-Step Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/sxidsvit/ai-repwise.git
   cd ai-repwise
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env.local` file in the root directory:

   ```env
   # App URL
   NEXT_PUBLIC_APP_URL=http://localhost:3000

   # Neon Postgres & Drizzle
   DATABASE_URL=postgres://user:password@ep-cool-name.neon.tech/repwise?sslmode=require

   # Better Auth
   BETTER_AUTH_SECRET=your_better_auth_secret

   # ImageKit
   NEXT_PUBLIC_IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
   IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
   NEXT_PUBLIC_IMAGEKIT_URL_ENDPOINT=https://ik.imagekit.io/your_imagekit_id

   # Stream (Chat & Video)
   NEXT_PUBLIC_STREAM_API_KEY=your_stream_api_key
   STREAM_SECRET=your_stream_secret_key

   # Stripe
   STRIPE_SECRET_KEY=your_stripe_secret_key
   NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
   ```

4. **Run Database Migrations:**

   ```bash
   npx drizzle-kit push
   ```

5. **Start the Local Development Server:**

   ```bash
   npm run dev
   ```

6. Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🌐 Deployment

### Cloudways Velocity / Automated CI/CD

1. Connect your repository branch (`master` / `main`) to **Cloudways Velocity**.
2. Configure all environment variables in the Cloudways dashboard.
3. Push to `master`. Cloudways will trigger automated builds and rollouts.

---

#### 🙏 Acknowledgements

This project is a version of the original project [Outpost](https://www.youtube.com/watch?v=-QCBtAfPHo0).

A heartfelt thank you to [Codesistency](https://www.youtube.com/@codesistency) for his invaluable contributions.

I used it for educational purposes to study its device in detail and created detailed technical documentation.
