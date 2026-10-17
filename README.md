# FleetOS — Transport & Logistics Management Prototype

A Next.js App Router / React / TypeScript / Tailwind interactive concept prototype for a transport company and multi-tenant transporter network.

## Start

```bash
npm install
npm run dev
```

Open http://localhost:3000. Deploy the project root to Vercel (Next.js preset).

## Demonstrable flows

- Role selector: Super Admin, Operations Staff, Accounts Staff, Read-Only Staff, Transporter Owner, Transporter Staff
- Transporter switcher for isolated partner-view demonstration
- Admin dashboard, operations pulse, KPIs, shipment pipeline
- RFQ creation, distribution to multiple groups with deduplication, quote submission in partner mode, confidential comparison and one-time award
- Award creates a shipment; direct booking creation
- Shipment tracking, milestones, exception status, vehicle/driver assignment with collision warnings
- POD submission and admin approval (status-only demo)
- Customer, transporter and group management
- Fleet, drivers, compliance expiry highlights
- Customer invoice payments, transporter settlement approvals/partial payments
- Reports and CSV export
- Browser localStorage persistence and reset

## Important boundaries

This is **not** a production backend. All records are fictional. The app runs in a browser, persists to localStorage, and simulates permissions only in the UI. Do not enter sensitive data or use it for live payments. There is no real login, server authorization, database, file upload, external notification, GPS, or bank payout.

## Production architecture recommendation

Next.js (App Router) + TypeScript frontend; NestJS REST API + PostgreSQL + Prisma/Drizzle; Redis/BullMQ for notifications; S3-compatible private storage; RBAC/ABAC enforced in API and database; append-only audit events; tenant-scoped queries; transactional award locks; separate operational, document, and finance states; migrations, backups, monitoring and tests.

## First-release roadmap

1. Discovery: roles/permissions matrix, workflow diagrams, data model, commercial terms and acceptance criteria.
2. Identity/tenancy: secure sessions, permissions, transporter isolation, audit logs.
3. Customers, transporters, groups and RFQ workflows with transactional allocation.
4. Bookings, assignments, trip milestones, POD, document storage and exceptions.
5. Invoices, payments, expenses, approvals and settlements.
6. Reports, notifications, QA, staging, production deployment and documentation.

Estimate GPS, driver mobile app, WhatsApp/SMS, payment gateway, accounting/government integration, complex P/LTL consolidation and route optimization separately.
