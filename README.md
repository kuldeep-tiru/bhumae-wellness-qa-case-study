# Bhumae Wellness E-commerce QA Case Study (Manual Testing)

Freelance quality assurance project for **TechSewak**: end-to-end testing of the live **Bhumae Wellness** website ([bhumaewellness.com](https://bhumaewellness.com)), a D2C botanical wellness store in India. Testing covered the customer storefront, checkout, order emails, order tracking and the store admin panel.

This case study documents manual QA work done for the TechSewak team on the Bhumae Wellness e-commerce platform (org repository, private).

> Published with the approval of the client. Security-related findings, order details and personal data are not included.

## At a glance

| | |
| --- | --- |
| Role | Freelance QA Tester (manual) |
| Company | TechSewak |
| Client website | Bhumae Wellness |
| Period | 9 to 13 October 2026 (test design on 9 Oct, execution 10 to 13 Oct) |
| Environment | Live production site, mobile and desktop |
| Effort | About 8 hours designing test cases and 30 hours executing and reporting |
| Tools | Excel test plan, Chrome DevTools, real Android and iPhone devices, Chrome, Edge and Firefox |

## Scope

- Catalog, collection filters, search and product pages
- Bag drawer, quantity limits, free-shipping threshold, GST-inclusive totals
- Checkout form validation, PIN code serviceability, Cash on Delivery rules and discount codes
- Order confirmation email, store alert email, order tracking and tax invoice
- Admin panel: orders, products, stock, discount codes, content and session handling
- Responsive layout and cross-browser checks on Android, iPhone and desktop

Out of scope (client decision): online payment gateway, SMS sign-in, courier booking and live tracking, load and penetration testing.

## Approach

1. **Requirement analysis.** Read the client's 35-check test plan, reviewed screenshots of every page and mapped each client check to a test case for traceability.
2. **Test design.** Added 78 cases beyond the client's plan using boundary value analysis, equivalence partitioning, negative testing, state and session checks, and data-consistency checks across storefront, email, tracking, admin and invoice.
3. **Execution.** Ran cases on the live site with real orders, cancelling every test order and restoring all data afterwards.
4. **Defect reporting.** Logged each defect with steps, actual and expected result, severity, priority, device and browser, and screenshots.
5. **Early observations.** Raised 23 non-defect questions (pricing rules, tax display, payment messaging, content) for client decision before launch.
6. **Regression.** Re-ran a 61-case high-priority set.

## Results

| Measure | Result |
| --- | --- |
| Test cases | 113 (35 from the client plan, 78 added) |
| Priority split | 61 High, 44 Medium, 8 Low |
| Executed | 103 (94 passed, 9 failed) |
| Blocked / not applicable | 8 blocked pending client clarification, 2 not applicable |
| Defects logged | 14 (9 Major, 5 Minor) |
| Regression set | 61 cases |
| Test types covered | 22, including functional, negative, boundary, validation, data integrity, security, compatibility, email and admin |

## Sample defect reports

### Buy Now ignores the selected quantity (Major / High)
- **Steps:** open a product page, set quantity 3, click Buy Now, check the quantity on checkout.
- **Actual:** quantity on checkout is 1.
- **Expected:** checkout uses the selected quantity.

### Order placed with a mismatched PIN code and city (Major / High)
- **Steps:** add an item, go to checkout, enter valid details, enter PIN 110001 and city Indore, place the order.
- **Actual:** no mismatch warning and the order is placed.
- **Expected:** the mismatch is flagged and the order is not placed.
- **Impact:** wrong tax split on the invoice and delivery errors.

### Admin accepts a selling price above the MRP (Major / High)
- **Steps:** open Add New Product, enter a selling price higher than the MRP with valid values elsewhere, save.
- **Actual:** the product is saved and listed.
- **Expected:** validation blocks saving and shows a clear message.

### Invalid URLs show the home page instead of a 404 (Minor / High)
- **Steps:** open two non-existent URLs.
- **Actual:** the home or collection page is shown for each.
- **Expected:** a proper 404 page.

## What this project shows

- Turning a client checklist into a traceable, risk-based test plan
- Finding gaps the client's plan did not cover (COD fee, GST treatment, validation, session handling)
- Clear, reproducible defect reports and professional communication of open questions
- Working within a tight deadline on a live production system without leaving test data behind

## Files

- [`docs/Bhumae_Wellness_QA_Test_Plan.xlsx`](docs/Bhumae_Wellness_QA_Test_Plan.xlsx): test plan with summary, execution plan, coverage by test type, 113 test cases and the regression set. Actual results, defect log and internal notes are not included.

## Author

Kuldeep Tiru, QA Professional. [LinkedIn](https://linkedin.com/in/kuldeep-tiru) | [GitHub](https://github.com/kuldeep-tiru)
