# Phase 1 — V2.1 Implementation Scope and Test Plan

**Status:** Approved work plan. This document records intended implementation and acceptance checks; it does not claim that the checklist has been completed.  
**Branch boundary:** Work only on `ambarisha-v2-testing`. Do not modify `main`, merge branches, deploy, change Netlify settings, access real client submissions, contact clients, or introduce paid services. Stop for owner approval if work could affect production, client data, payment processing, or third-party services.

## Approved scope

1. Improve responsive mobile navigation, accessibility, keyboard interaction, and reduced-motion behavior while preserving the existing website design and branding.
2. Prepare a privacy notice draft and consent mechanism for owner review. Do not publish unapproved legal wording, present the draft as an approved policy, or apply an arbitrary retention period.
3. Preserve existing Netlify booking form field names and submission compatibility.
4. Review WhatsApp links, Netlify Forms markup/configuration, and the `/thank-you` route without contacting real clients or inspecting real submissions.
5. Establish lightweight automated local tests using fictional client data exclusively.
6. Document six coordinated AI-agent responsibilities, handoffs, review requirements, and conflict resolution.
7. Keep future Vedic astrology calculations and SALSA methodology distinct, with separate review and approval stages.

## Implementation checklist

### Website and accessibility
- [ ] Add responsive mobile navigation using accessible controls and state (`aria-expanded`, `aria-controls`, descriptive labels).
- [ ] Support keyboard operation, visible focus, Escape dismissal, and sensible focus return.
- [ ] Provide a skip link and verify page landmarks, heading hierarchy, form labels, and link names.
- [ ] Respect `prefers-reduced-motion` for decorative animation.
- [ ] Preserve the current visual identity and existing content unless a separate owner-approved change is made.

### Privacy and consent
- [ ] Add a clearly marked **draft for owner review**, not an approved legal policy.
- [ ] Explain the collected booking fields and proposed purpose in plain language, subject to owner approval.
- [ ] Add an explicit, unchecked consent control only after its wording and required/optional behavior are approved.
- [ ] Document retention and deletion as a proposed workflow with the retention period explicitly **to be decided by the owner**.
- [ ] Do not claim that retention, deletion, or privacy controls are technically enforced unless verified and approved.

### Forms, routing, and links
- [ ] Preserve existing form field names: `name`, `email`, `whatsapp`, `birth_date`, `birth_time`, `birth_place`, and `questions`; retain `subject` and honeypot behavior.
- [ ] Review `data-netlify`, form name, method, action, and honeypot markup without changing Netlify account settings.
- [ ] Check the `/thank-you` route against `public/thank-you.html` in local testing; do not submit real bookings.
- [ ] Validate WhatsApp `wa.me` destinations and URL-encoded prefilled text without sending messages.
- [ ] Mark dashboard-dependent behavior (notifications, spam filtering, retention, deploy context) as unverified unless independently confirmed with owner approval.

### Automated tests and documentation
- [ ] Add a lightweight local test setup that does not require paid services.
- [ ] Use fictional fixtures only; never use real client details, payment references, or submissions.
- [ ] Document six agent roles, responsibilities, handoffs, review gates, and conflict resolution.
- [ ] Document future astrology-report phases; keep Vedic calculations and SALSA methodology in separate workstreams and review gates.

## Testing requirements and acceptance checks

Run tests locally or in an explicitly approved non-production preview. Do not deploy as part of this plan.

- [ ] Static markup/configuration checks pass, including form-name and field-name compatibility checks.
- [ ] Browser checks cover desktop and narrow/mobile viewport layouts.
- [ ] Mobile navigation opens/closes by pointer and keyboard; Escape closes it; focus remains visible and returns appropriately.
- [ ] Skip link, landmarks, headings, labels, accessible names, and reduced-motion behavior are verified.
- [ ] Booking validation and consent state are checked with synthetic test values only.
- [ ] The local form flow reaches the expected thank-you page without contacting Netlify production or creating a real submission.
- [ ] WhatsApp links are checked for valid destination and encoded message; no message is sent.
- [ ] Automated accessibility checks are supplemented by manual keyboard review; findings and limitations are recorded.
- [ ] Test fixtures and reports contain fictional data only.
- [ ] Record the exact commands, environment, outcomes, and any failures; do not describe unrun tests as passed.

## Review gates and unresolved owner decisions

Owner approval is required before publishing privacy/consent wording, deciding consent behavior, setting a retention period, changing Netlify dashboard settings, adding a paid service, or taking any production-impacting action. Business decisions such as privacy contact details, deletion-request handling, approved retention duration, and policy jurisdiction remain unresolved until the owner decides them.

A Phase 1 implementation is complete only after the checklist has been carried out, actual test results documented, and the work reviewed on `ambarisha-v2-testing`. This plan does not authorize deployment or merging.
