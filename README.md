# Freelancer-portal

The **freelancer-facing** product for Wisemonk — the portal a freelancer/contractor uses to onboard, log in, and manage their own work, invoices and payments.

This is the counterpart to **[Client-freelancer](https://github.com/AnjuChorotiya/Client-freelancer)**, which is the *client-facing* product (where clients add and manage their freelancers). Anything seen from the **freelancer's** perspective lives here.

## Hosting

- Static, framework-free HTML/CSS/JS — no build step.
- Hosted on GitHub Pages: `https://anjuchorotiya.github.io/Freelancer-portal/`
- Built on the shared **Wisemonk UI** design system (`wisemonk-ui/`) — official palette, Satoshi + Open Sans Light type, Iconsax (vuesax linear) icons. CSS classes prefixed `wm-`, tokens `--wm-`.

## The freelancer flow

The freelancer journey is the **"I'm looking to get paid"** path:

```
login.html → check-inbox.html → signup-role.html  → signup-country.html → freelancer-onboarding.html
  (sign up)    (verify email)    (pick "get paid")    (?role=freelancer)     (self-onboarding)
```

`signup-role.html` and `signup-country.html` are shared with the client product but are role-aware: choosing **"I'm looking to get paid"** routes to `signup-country.html?role=freelancer`, which lands on `freelancer-onboarding.html`.

## Screens

| Page | Purpose | Live Preview |
|---|---|---|
| [login.html](login.html) | Sign up / log in | https://anjuchorotiya.github.io/Freelancer-portal/login.html |
| [check-inbox.html](check-inbox.html) | Verify email | https://anjuchorotiya.github.io/Freelancer-portal/check-inbox.html |
| [signup-role.html](signup-role.html) | Role selection — "I'm looking to get paid" | https://anjuchorotiya.github.io/Freelancer-portal/signup-role.html |
| [signup-country.html](signup-country.html) | Country selection (role=freelancer) | https://anjuchorotiya.github.io/Freelancer-portal/signup-country.html?role=freelancer |
| [freelancer-onboarding.html](freelancer-onboarding.html) | Freelancer self-onboarding | https://anjuchorotiya.github.io/Freelancer-portal/freelancer-onboarding.html |
| [dashboard.html](dashboard.html) | Freelancer home — payouts, balance, activity (modals: bank details · invite client · request payment). Empty state: `?empty` | https://anjuchorotiya.github.io/Freelancer-portal/dashboard.html |

See [SCREENS.md](SCREENS.md) for per-screen detail and the screens still to build.

## Roadmap (freelancer-facing screens to build)

- Freelancer dashboard / home
- My invoices — raise & track invoices to clients
- Payments & wallet
- Compliance & documents (the freelancer's own)
- Profile / settings
