<div align="center">
  <img src="https://raw.githubusercontent.com/arukinSec/frontend/master/public/arukin-og.jpg" alt="Arukin Banner" width="100%">
</div>

<br>

# Arukin Security

Arukin is an advanced security monitoring and account management gateway designed specifically for at-risk persons (including vulnerable adults, the elderly, or targets of cyberstalking). It provides a "Trusted Guardian" console for managers to safely steward Google Workspace environments.

## Core Philosophy

Arukin relies on a Zero-Install security model. Vulnerable users do not need to install mobile apps, browser extensions, or endpoint management software. Instead, it integrates directly with Google Cloud OAuth. Managers can remotely audit and steward Gmail, Google Drive, and Google Contacts data.

## Open Source Repositories

This organization houses the complete Arukin architecture:

* **[frontend](https://github.com/arukinSec/frontend)**: The secure React and Vite based client dashboard.
* **[supabase](https://github.com/arukinSec/supabase)**: The backend architecture containing PostgreSQL schemas, Row-Level Security policies, and Deno Edge Functions.
* **[docs](https://github.com/arukinSec/docs)**: The comprehensive technical documentation for the entire platform.

## Architecture Highlights

* **Server-Side API Proxying**: To eliminate token leakage, the frontend never connects to Google APIs directly. All requests are routed through a backend Supabase Edge Function proxy.
* **AES-GCM Client Caching**: Uses the Web Crypto API to securely encrypt cached API responses in the browser's IndexedDB.
* **Strict Privacy via RLS**: Enforces tenant isolation securely at the database level using PostgreSQL Row-Level Security.

Arukin provides the tools necessary for modern, frictionless, and secure stewardship of vulnerable digital lives.
