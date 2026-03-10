# ISLA Gaia Library System

<div align="center">

**A full-stack digital library management platform built for ISLA Gaia university.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-biblioteca--islagaia.pt-blue?style=for-the-badge&logo=globe)](https://biblioteca-islagaia.pt)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=node.js)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=for-the-badge&logo=mysql)](https://www.mysql.com)

</div>

---

## Overview

The ISLA Gaia Library System is a full-featured web application that digitizes and streamlines all library operations at ISLA Gaia university. It supports the complete lifecycle of library resources — from cataloguing and searching to loans, reservations, and returns — while providing role-specific dashboards for students, librarians, and administrators.

> **Live at:** [biblioteca-islagaia.pt](https://biblioteca-islagaia.pt)

---

## Key Features

### For Students
- **Book Catalogue** — Browse and search the full library catalogue by title, author, or category
- **Book Details** — View cover images, descriptions, availability, and read integrated PDFs
- **Reservations** — Reserve unavailable books and receive automatic notifications when they become available
- **Loan History** — Track active loans, due dates, and borrowing history
- **Favorites** — Save books to a personal favourites list
- **Profile Management** — Update personal information and change password securely

### For Librarians
- **Loan Management** — Create, extend, and process returns for physical loans
- **Reservation Processing** — Convert reservations to active loans when books are returned
- **Fine Management** — Track and manage overdue fines

### For Administrators
- **Book Management** — Add, edit, and remove books with cover images and PDF files
- **Author & Category Management** — Manage the full taxonomy of the catalogue
- **User Management** — Create, edit, and deactivate user accounts with role assignment
- **Audit Logs** — Full audit trail of all system actions with timestamps and user attribution
- **Reports** — Generate reports on loans, reservations, and library activity

### System-wide
- **Multi-language Support** — Full interface in Portuguese, English, Spanish, and French
- **Email Notifications** — Automated emails for loan confirmations, overdue reminders, and reservation availability
- **Scheduled Tasks** — Automated cron jobs for overdue detection and reservation expiry
- **LDAP Integration** — Institutional authentication support
- **Responsive Design** — Fully usable on desktop, tablet, and mobile

---

## Technology Stack

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express | REST API server |
| MySQL 8 | Relational database |
| JWT | Stateless authentication |
| Multer | File uploads (covers & PDFs) |
| Nodemailer | Email notifications |
| node-cache | In-memory caching |
| Helmet + CORS + Rate Limiting | Security hardening |

### Frontend
| Technology | Purpose |
|---|---|
| React 18 | UI framework |
| TypeScript | Type-safe development |
| Vite | Build tooling |
| TailwindCSS | Utility-first styling |
| React Router v7 | Client-side routing |
| Lucide React | Icon library |
| react-hot-toast | User notifications |

---

## Architecture

```
┌─────────────────────────────────────┐
│          Frontend (React)           │
│  Components · Pages · Services      │
│  Contexts · Hooks · i18n            │
└──────────────┬──────────────────────┘
               │ HTTPS / REST API
┌──────────────▼──────────────────────┐
│       Backend API (Express)         │
│  Routes · Middleware · Models       │
│  Services · Utils                   │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│          Database (MySQL)           │
│  Tables · Stored Procedures         │
│  Triggers · Audit Tables            │
└─────────────────────────────────────┘
```

---

## Role-Based Access Control

The system enforces three distinct roles with scoped permissions:

| Feature | Student | Librarian | Admin |
|---|:---:|:---:|:---:|
| Browse catalogue | ✅ | ✅ | ✅ |
| Read PDFs | ✅ | ✅ | ✅ |
| Make reservations | ✅ | ✅ | ✅ |
| Manage loans | ❌ | ✅ | ✅ |
| Manage books | ❌ | ✅ | ✅ |
| Manage users | ❌ | ❌ | ✅ |
| View audit logs | ❌ | ❌ | ✅ |
| System reports | ❌ | ❌ | ✅ |

---

## Internationalization

The full interface is available in three languages, switchable at runtime without a page reload:

- 🇵🇹 **Portuguese** (default)
- 🇬🇧 **English**
- 🇪🇸 **Spanish**
- 🇫🇷 **French**

---

## Project Status

The system is actively deployed and in production use at [biblioteca-islagaia.pt](https://biblioteca-islagaia.pt).

---

<div align="center">
  Built by <a href="https://github.com/DFRSfx">Dário Soares</a> · ISLA Gaia · 2025–2026
</div>
