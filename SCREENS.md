# Screens — Freelancer-portal

Per-screen documentation (purpose · flow · validations) for the freelancer-facing product.

## login.html
**Purpose:** Sign up / log in entry point.
**Flow:** Submit → `check-inbox.html?email=…`.

## check-inbox.html
**Purpose:** Email verification step.
**Flow:** Verify → `signup-role.html`.

## signup-role.html
**Purpose:** Role selection. The freelancer picks **"I'm looking to get paid"** (sign contracts, send invoices, get paid in local currency). The other card ("I want to pay & manage freelancers") belongs to the client product.
**Flow:** "I'm looking to get paid" → `signup-country.html?role=freelancer`.

## signup-country.html
**Purpose:** Country selection, role-aware copy.
**Flow:** With `role=freelancer` → `freelancer-onboarding.html?country=<code>`.

## freelancer-onboarding.html
**Purpose:** A freelancer onboards themselves into Wisemonk (profile, payout, compliance details).
**Flow:** Reached from `signup-country.html`. On completion the freelancer reaches their dashboard.

---

## To build
- **Freelancer dashboard / home** — overview of contracts, pending invoices, upcoming payments.
- **My invoices** — freelancer raises and tracks invoices to clients.
- **Payments & wallet** — payout history, balances.
- **Compliance & documents** — the freelancer's own KYC / tax / contract docs.
- **Profile / settings** — personal and payout details.
