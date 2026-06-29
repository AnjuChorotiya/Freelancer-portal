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
**Flow:** Reached from `signup-country.html`. On completion the freelancer reaches `dashboard.html`.

## dashboard.html
**Purpose:** The freelancer home / workspace. Shows the at-a-glance summary once onboarding is done.
**Sections:**
- **Stat cards** — Upcoming payout, Pending request, Active clients.
- **Available balance** — masked payout account + balance; the card *and* the (i) icon open the **Bank account details** modal.
- **Recent Activity** — payment/request feed with status badges (Processed · Approved). Empty state shows a "No activity to display" illustration.
**Actions / modals:**
- **Request Payment** — modal (Client · Amount · Note); enabled when a client and a positive amount are set.
- **Invite client** — modal (Client company name · Contact name · Work email); Invite enabled only when all three are filled and the email is valid.
- **Bank account details** — read-only payout-account details with a Done button.
**States:** add `?empty` to the URL for the new-freelancer empty state (zeroed stats, USD 0.00, empty activity).
**Validations:** Invite requires a valid email; Request Payment requires client + amount > 0.

## clients.html
**Purpose:** The freelancer's client list — agreements, billing models and status at a glance.
**Table:** Client name · Model (DCP / CoR) · Start date · Status (Invited · Active) · row actions (kebab → view / edit / remove).
**Actions:** **Invite Client** opens the invite modal (company · contact · work email; enabled when all filled + valid email). Search filters rows live.

## requests.html (Invoices)
**Purpose:** Track invoices raised to clients and their payment status. Nav label is **Requests**; the page is titled **Invoices**.
**Stats:** Total outstanding · Processing · Paid this month.
**Table — Invoice history:** Invoice # (link) · Client · Issue date · Credit date · Amount · Status (Paid · Processing · Awaiting · Approved · Rejected) · row actions.
**Controls:** live search + **All status** dropdown (filters the table by status). **Request payment** opens the request modal (client · amount · note; enabled when client + amount > 0).

## payments.html
**Purpose:** History of settled earnings paid out to the freelancer.
**Table:** Payment date · Currency · Amount · row actions (view receipt / download statement).
**Controls:** live search + **All time** date-range selector.

---

## To build
- **Freelancer dashboard / home** — overview of contracts, pending invoices, upcoming payments.
- **My invoices** — freelancer raises and tracks invoices to clients.
- **Payments & wallet** — payout history, balances.
- **Compliance & documents** — the freelancer's own KYC / tax / contract docs.
- **Profile / settings** — personal and payout details.
