# ByeChargeBack Custom Dashboard

A WordPress plugin that provides a full custom user dashboard for **ByeChargeBack** — signup flow, sign-in, credits pricing, billing, alerts, and admin-configurable branding.

**Version:** 1.2.2  
**Requires:** WordPress 6.0+, PHP 7.4+

---

## Features

### Frontend
- **Homepage CTA** — configurable button linking to signup or dashboard
- **3-step signup flow** — intro → email capture → check inbox
- **Email sign-in** — HTML welcome email with credentials and sign-in link
- **User dashboard** — account menu, + Credits modal, pricing table, FAQ, testimonial
- **Dispute tips & alerts** — popovers with unlock flow when credits are empty
- **Protect Account** — configurable error messages on activation attempt
- **Mobile responsive** — works on all screen sizes
- **Distraction-free UI** — WordPress admin bar hidden on plugin pages

### Admin
- Brand name, email, logo, logout redirect URL
- Page assignment for Get Started, Sign In, and Dashboard
- Highlight colors for rules and tooltips
- Credits modal content (headline, benefits, promo banner)
- Pricing tiers (4 plans) with standard and deal checkout links
- FAQ, testimonial, dispute tips, and protect-account error messages

---

## Installation

1. Copy the `bye-chargeback-dashboard` folder to:
   ```
   wp-content/plugins/bye-chargeback-dashboard/
   ```
2. Activate **ByeChargeBack Custom Dashboard** in **Plugins**.
3. On activation, three pages are created automatically:
   - Get Started
   - Sign In
   - Dashboard
4. Go to **BCB Dashboard** in wp-admin and configure branding, pricing links, and content.

---

## Shortcodes

| Shortcode | Description |
|-----------|-------------|
| `[bcb_home_button]` | Homepage CTA (links to Get Started, or Dashboard if logged in) |
| `[bcb_get_started]` | 3-step signup flow |
| `[bcb_sign_in]` | Sign-in screen (linked from welcome email) |
| `[bcb_dashboard]` | Main dashboard (requires login) |

### Optional attributes

```
[bcb_home_button text="Protect My Business" url="https://yoursite.com/get-started/"]
```

---

## Admin settings

Open **BCB Dashboard** in the WordPress admin menu.

| Section | What you configure |
|---------|-------------------|
| **Brand** | Name, email, logo, logout redirect URL |
| **Pages & Shortcodes** | Assign Get Started, Sign In, and Dashboard pages |
| **Highlight Colors** | Text and background colors for rule/tooltip tags |
| **Credits Modal** | Headline, benefits, promo banner, discount code & % |
| **Pricing & Links** | 4 tiers + Buy Plan / Get Deal URLs per tier |
| **Dashboard Tooltips** | Labels and tooltip text for dashboard rules |
| **Protect Account Errors** | Messages shown when protection fails |
| **Dispute Tips** | Tips list and unlock message |
| **FAQ & Testimonial** | Modal content |

### Default brand

- **Name:** ByeChargeBack  
- **Email:** contact@ByeChargeBack.com  
- **Logout redirect:** https://byechargeback.com/

### Color palette

| Name | Hex |
|------|-----|
| Regal Navy | `#134074` |
| Oxford Navy | `#13315C` |
| Prussian Blue | `#0B2545` |
| Powder Blue | `#8DA9C4` |
| Mint Cream | `#EEF4ED` |

---

## Project structure

```
bye-chargeback-dashboard/
├── bye-chargeback-dashboard.php   # Plugin bootstrap
├── includes/
│   ├── class-bcb-settings.php     # Settings & defaults
│   ├── class-bcb-admin.php          # Admin menu & settings page
│   ├── class-bcb-frontend.php       # Shortcodes & templates
│   ├── class-bcb-ajax.php           # AJAX handlers
│   └── class-bcb-mail.php           # Email delivery
├── templates/
│   ├── admin/settings-page.php
│   └── frontend/
│       ├── dashboard.php
│       ├── get-started-flow.php
│       ├── sign-in.php
│       └── partials/pricing-table.php
├── assets/
│   ├── css/frontend.css
│   ├── css/admin.css
│   ├── js/frontend.js
│   └── js/admin.js
└── readme.txt                     # WordPress.org readme
```

---

## Local development

When running on **Local WP** (or any environment with `WP_ENVIRONMENT_TYPE=local`):

- Sign-in emails are sent to **MailHog** — open **Tools → MailHog** in Local
- No real emails are delivered until you configure SMTP on production

For production, use an SMTP plugin (e.g. WP Mail SMTP) for reliable email delivery.

---

## User flow

```
Homepage [bcb_home_button]
    → Get Started [bcb_get_started]
        → Step 1: Intro
        → Step 2: Enter email
        → Step 3: Check inbox
    → Sign In [bcb_sign_in] (from email link)
    → Dashboard [bcb_dashboard]
        → + Credits modal
        → Protect Account
        → Billing / Account menu
        → Log out → byechargeback.com
```

---

## License

GPLv2 or later

---

## Author

[ByeChargeBack](https://byechargeback.com/)
