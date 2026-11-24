# Smart Campus Market System (SCMS)

MGT3151 E-Business, E-Commerce and E-Governance | Project Direction B (E-Commerce) | Group XX | Advent 2026

SCMS is a web-based marketplace where verified university students buy from verified campus vendors. This repository is a **bounded functional prototype**, not a production system. All data is fictitious and all payments are mocked.

## Features

- Registration and login. Students are verified by campus email (`@ucu.ac.ug` or `@stud.ucu.ac.ug`, a mock check). Vendors must be approved by an admin.
- Search and category filter with live stock.
- Cart with stock limits.
- Mock checkout (sandbox). A "simulate declined payment" option tests the failure path.
- One order per vendor, moved through Placed, Packed, Ready for pickup and Delivered.
- After-sales: cancel while Placed, return request, vendor accepts or rejects, rating.
- Vendor dashboard (products, stock, incoming orders) and admin console (vendor verification, all orders, audit log).

## Demo accounts (fictitious)

| Role | Email | Password |
|---|---|---|
| Student | student@stud.ucu.ac.ug | Student#1234 |
| Vendor | vendor@scms.test | Vendor#1234 |
| Admin | admin@scms.test | Admin#1234 |

## Requirements

- A modern browser (tested on: [Chrome version], [Firefox version], [Edge version]; fill in your own).
- No installation, build step or server is required. There are no external libraries or network calls.

## Setup and run (reproduce the demo)

1. Clone or unzip the repository.
2. Open `index.html` in a browser (double-click it).
3. Log in with a demo account above.

Optional local server (any one of these):

```bash
python3 -m http.server 8000      # then open http://localhost:8000
```

Optional hosting: upload the folder to any static host (for example GitHub Pages) and open the published URL. Hosted URL: [add link].

## Suggested demo walkthrough (about 5 minutes)

1. Register a new student (use a campus email). Register a new vendor, then log in as admin and verify the vendor.
2. Log in as the student. Search for "notebook", add items to the cart and check out with a mock method.
3. Try a declined payment (tick "Simulate a declined payment"). No order is created.
4. Log in as the vendor. Move the order through Placed, Packed, Ready for pickup and Delivered.
5. Log in as the student. Request a return and rate the order. Log back in as the vendor and accept the return.
6. Log in as admin and review the audit log.

## Repository structure

```
smart-campus-market/
  index.html          # the whole prototype (UI, logic, demo data)
  README.md           # this file
  docs/               # report PDF/Word, slides, diagrams (BPMN, architecture, ERD)
  tests/              # test cases sheet and screenshots (evidence)
  data/               # sample fictitious data and schema scripts
```

## Data storage and reset

State is stored in the browser's `localStorage` under the key `scms_v1`. To reset: log in as admin and use **Reset demo data**, or clear site data in the browser. Data is per browser and per device.

## Testing

The test plan is in the report (section 16): 10 cases (6 positive, 3 validation or error, 1 access control). Record actual results and screenshots in `tests/`.

## Security and privacy notes

- Role checks on every page and action; vendors can only change their own products and orders.
- Input validation (email, password strength, price, stock, quantity) and escaped output against script injection.
- Login lockout after 5 failed attempts; audit log of key actions.
- Only fictitious data and mock payments. No real card, mobile-money PIN, OTP, identity, medical or biometric data.

## Known limitations

- Browser-only storage and a demo-level password hash. Production needs a server, a database, bcrypt or argon2 hashing and HTTPS.
- Payments are mocked and there is no real email or SMS notification.
- No synchronisation across devices.

## Team and contributions

| Member | Student no. | Role | Main contribution | Commits / issues |
|---|---|---|---|---|
| [name] | [no.] | [role] | [work] | [links] |

Each member must be able to explain and defend their own work. See the role matrix and contribution statements in the report appendices.

## Generative AI use

Generative AI helped with [prototype code, report structure, slide outline]. The group reviewed, tested and modified the output. Full declaration: report Appendix B.

## References and credits

- [Add libraries, datasets, diagrams and external material reused, or state that none were used.]

## Licence

Coursework submission for MGT3151, Uganda Christian University. [Add licence or "All rights reserved" as agreed by your group.]
