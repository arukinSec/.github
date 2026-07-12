<div align="center">
  <img src="https://raw.githubusercontent.com/arukinSec/frontend/master/public/arukin-og.webp" alt="Arukin Banner" width="100%">
</div>

<br>


# Arukin Security

Arukin is an advanced security monitoring and account management gateway designed specifically for at-risk persons (including vulnerable adults, the elderly, or targets of cyberstalking). It provides a "Trusted Guardian" console for managers to safely steward Google account environments.

> [!CAUTION]
> **Experimental Status & Dual-Use Warning**
> Arukin is currently in an experimental beta phase.
> 
> * **AI-Generated Documentation:** Project documentation and marketing pages are compiled with the assistance of AI coding agents. Consequently, these materials may sometimes be more aspirational than factual, occasionally referencing roadmap goals or hallucinating features before they are fully merged into the production branch.
> * **Consent Safeguards:** Core utility features are currently prioritized over authorization safeguards. This tool can technically be misconfigured or misused for non-consensual tracking as stalkerware. Non-consensual monitoring is strictly prohibited.

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

## Security Safeguard Roadmap

To actively address consent and potential misuse concerns, technical safeguards are organized into immediate and long-term release cycles:

### Upcoming Update (Next Release)

These immediate features will be enforced via a granular **permission request step** during account pairing, giving member users direct control over their sharing options:

* **Gmail Deletion Delay:** Immediate deletion of Google security alerts from Gmail will be blocked. Deletions will be restricted by a mandatory 1-week time-lock, ensuring member users have a clear window to read critical account alerts. Member users can explicitly choose whether to grant the manager read/write permissions for these security alert emails.
* **Sensitive Email Filtering:** One-Time Password (OTP) and password-reset emails will be filtered out and hidden from the manager console entirely to protect authentication integrity. Member users can choose to enforce these filters or opt to share them.

### Future Development (Long-Term Roadmap)

* **Mandatory Email Verification Delay:** An email-based verification process will enforce a mandatory 24-hour waiting period before any account pairing is authorized. The pairing invitation link only becomes active *after* the 24-hour delay and remains valid for a strict 12-hour window, ensuring the authentication grant is intentional. 
* **Member Blocklist & Strikes:** Member users will have the option to permanently block specific manager emails from requesting access. Managers who accumulate a set threshold of these blocks (strikes) will be permanently banned from the platform.
* **Google Family Bypass:** If supported by future Google API integrations, the 24-hour waiting period may be bypassed for verified members of the same Google Family Group, where a pre-existing trust relationship is established. (These verification features are deferred pending custom domain configuration).

Detailed development plans and the project roadmap will be published directly within the [frontend](https://github.com/arukinSec/frontend) repository in the future.
