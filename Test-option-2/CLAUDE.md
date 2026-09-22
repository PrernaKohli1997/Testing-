# UCV — Unified Conversations View

Inbox/messaging prototype for Tekion's dealership CRM: nav rail (My Inbox / All Inbox / AI Activity / Unassigned + saved views) → conversation list → chat panel, with AI-routing, escalation, assignee side sheet, and intent pills.

## Files
- `UCV v7.dc.html` — current/latest version, active in preview.
- `UCV v2–v6.dc.html` — prior iterations, kept for history. Don't edit; copy forward instead.
- Design system: DS - Arcade Design System, bundle loaded from `_ds/ds-arcade-design-system-c0f4b397-8115-4b82-a4ed-12760a937f5e/`.

## Conventions in this file
- Single DC, no child components — one large `<x-dc>` body with `Component` logic class.
- Mock data lives inline in the logic class: `allConvs`/base conversation array + `INCOMING_CONVS` (simulated new arrivals) + `NAV_HEADING` map.
- Conversations carry: `navTags` (which nav buckets they appear in), `filter` (unread/ai-routed/unknown/etc.), `assignee`/`coAssignees`, `channel` (phone/email/chat), `unread`, `intent`.
- Custom animations (shimmer, escalation pulse, badge fade) defined as `@keyframes` in the `<helmet><style>` block — kept minimal, no bounce/spring per DS motion rules.
- Icons: Phosphor `ph ph-*` classes via the DS `Icon`, plus two custom SVGs (`nav-unassigned.svg`, `nav-my-inbox.svg`, `nav-all-inbox.svg`) for nav glyphs not covered by Phosphor.
- Follow Arcade DS copy rules: Title Case for nav/buttons, sentence case for body/helper text, no emoji.

## When editing
- Match existing patterns (assignee side sheet, escalation timers, intent pills) rather than introducing new mechanisms.
- New iteration = copy `UCV v7.dc.html` to `UCV v8.dc.html` before a substantial redesign; small targeted fixes edit v7 in place.
