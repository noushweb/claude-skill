---
name: enkay-ux-audit
description: Audit UX for a specific flow, screen, component, or whole project. Use for usability reviews, flow problems, missing states, consistency, accessibility, and prioritized fixes. Ask whether to audit the whole project or a specific area, then ask which checks to run. Audit only selected checks and do not implement changes until approved.
---

# Enkay UX Audit

Audit UX from the perspective of a real user. Find usability problems, explain their impact, and recommend practical fixes.

Every recommendation must solve a user problem, reduce friction, improve clarity, improve accessibility, or help complete a task. Do not treat visual modernization as a UX goal.

## Rules

- Confirm scope before detailed auditing.
- When `/enkay-ux-audit` is invoked without a clear scope, ask whether to audit the whole project or a specific area.
- If a specific area is requested, first scan the project and list possible audit areas.
- Show the check-selection menu before running checks.
- Run only selected checks.
- Ground findings in observable UI, routes, components, labels, forms, states, or user actions.
- Separate facts from assumptions; label assumptions.
- Provide observable evidence for every finding; do not make generic claims.
- Do not redesign or implement changes until findings are approved.
- Prefer high-impact, minimal fixes over broad redesigns.
- Do not add features unless necessary for task completion.
- Do not prioritize visual polish by itself.
- After approved fixes, re-run the affected flow or task and confirm the issue is resolved without introducing new friction.

## Step 1: Choose audit scope

When `/enkay-ux-audit` is invoked without a clear scope, first ask whether the user wants a complete project audit or a specific-area audit.

Do not start detailed auditing yet.

Ask:

```text
What would you like to audit?

1. Complete project audit
2. Specific area, flow, screen, or component
3. Custom scope

Reply with 1, 2, or 3.
```

### If the user selects 1: Complete project audit

Create a high-level project map first:

- Product purpose
- Primary users
- Core features
- Main routes or screens
- Major user flows
- Shared components and patterns
- Forms, lists, dashboards, settings, and destructive actions

Then show the whole-project pass menu:

```text
Which project areas should I audit?

[ ] A. Global navigation, layout, and dashboard/home
[ ] B. Authentication and onboarding
[ ] C. Core create / edit / delete flows
[ ] D. Search, filters, lists, and detail views
[ ] E. Settings, account, and permissions
[ ] F. Admin or internal tools
[ ] G. Error, loading, empty, and recovery states
[ ] H. Cross-project consistency
[ ] I. Accessibility
[ ] J. Mobile / responsive experience

Reply with letters, or type "all".
```

Audit selected areas in passes. After each pass, show findings and ask whether to continue to the next pass.

### If the user selects 2: Specific area

First scan the project at a high level to identify possible audit areas.

Inspect project structure, routes, pages, components, navigation, documentation, and major features. Do not perform a detailed UX audit yet.

Create a concise list of audit areas:

```text
I found these possible areas to audit:

1. Authentication — /login, /signup, password reset
2. Dashboard — /dashboard
3. Project creation — /projects/new
4. Project list — /projects
5. Project details — /projects/:id
6. Settings — /settings
7. Checkout — /cart, /checkout
8. Search and filters — /search
9. Global navigation and layout

Which area would you like to audit?

Reply with a number, or type a custom area such as:
"checkout payment step", "mobile navigation", or "project deletion flow".
```

Rules:

- List only areas that actually exist in the project.
- Use route names, page names, or feature names from the project.
- Keep the list to 5–12 relevant areas.
- If there are more than 12 areas, group related screens into one area.
- If the user types a custom area, use that as the audit scope.
- If the requested area is unclear, ask one concise clarifying question.

### If the user selects 3: Custom scope

Ask:

```text
Describe the area you want to audit.

Examples:
- Checkout payment step
- Project creation form
- Mobile navigation
- Settings profile update
- Search and filters

Also tell me, if known:
- Main user
- Starting point
- What success looks like
```

After the user provides the custom scope, continue to Step 2.

## Step 2: Check-selection menu

After the scope is confirmed, show this checklist before auditing:

```text
Which UX checks should I run for: <scope>?

[ ] 1. User goal and success criteria
[ ] 2. Current flow mapping
[ ] 3. Friction, confusion, dead ends, and unnecessary steps
[ ] 4. Navigation and next-action clarity
[ ] 5. Form validation and field-level errors
[ ] 6. Loading states
[ ] 7. Empty states
[ ] 8. Success and confirmation states
[ ] 9. Error and failure recovery
[ ] 10. Destructive actions and undo
[ ] 11. Visual consistency
[ ] 12. Component and label consistency
[ ] 13. Accessibility
[ ] 14. Responsive / mobile experience
[ ] 15. Simulated first-time user test
[ ] 16. Prioritized issue report
[ ] 17. Audit whole project in passes

Reply with numbers. Example: 1, 2, 3, 6, 8, 9, 16
```

- If the user says “run everything” or “full audit,” run all relevant checks.
- If the user selects a subset, run only that subset.
- Do not run unselected checks unless essential to understand a selected issue.
- If check 17 is selected, ask which project areas to audit first.

## Step 3: Product context

Run only if checks 1 or 2 are selected, or if context is needed.

Inspect available product, code, routes, components, screenshots, and documentation. Summarize:

- Product purpose
- Primary users
- Main user goal
- Core features
- Main screens or flows
- Platform
- Constraints
- Assumptions and uncertainties

Ask the user to correct incorrect assumptions before continuing.

## Step 4: Run selected checks

For every finding, use:

```text
| Priority | Issue | Evidence | Why it matters | Recommended fix | Scope |
|---|---|---|---|---|---|
```

Use priorities:

- **P0:** Blocks an important task
- **P1:** Major confusion, repeated mistakes, or high friction
- **P2:** Meaningful clarity, speed, or ease-of-use improvement
- **P3:** Polish with limited task-completion impact

### 1. User goal and success criteria

Identify primary user, goal, success criteria, first-time confusion, premature or unnecessary information, confusing labels, and system-centered organization.

```text
Identify the primary user, goal, success criteria, first-time confusion,
unnecessary or premature information, confusing labels, and system-centered organization.
For each issue: location, evidence, problem, impact, and practical fix. Do not redesign.
```

### 2. Current flow mapping

Map the flow from start to success:

```text
USER GOAL:
STARTING POINT:
SUCCESS CRITERIA:
CURRENT FLOW:
1. ...
2. ...
UNCERTAINTIES:
```

```text
Map the current flow step by step. Include user goal, starting point,
success criteria, major steps, unclear steps, missing next actions, and uncertainties.
Do not redesign.
```

### 3. Friction and unnecessary steps

Find unnecessary steps, backtracking, dead ends, repeated work, information users must remember, confusing decisions, and system-centered organization.

```text
Find friction, confusion, dead ends, unnecessary steps, repeated work,
and information users must remember. For each issue: location, evidence,
problem, impact, and practical fix. Do not redesign.
```

### 4. Navigation and next-action clarity

Find unclear next actions, weak primary actions, confusing navigation, and places where users do not know where they are or how to go back.

```text
Audit navigation and next-action clarity. Find unclear next actions,
weak primary actions, confusing navigation, and missing back/cancel paths.
For each issue: location, evidence, problem, impact, and practical fix.
```

### 5. Form validation and field errors

Find missing validation, unclear labels, poor error placement, unhelpful messages, disabled-submit confusion, and weak recovery paths.

```text
Audit form validation and field-level errors. Find missing validation,
unclear labels, poor error placement, unhelpful messages, and weak recovery.
For each issue: location, evidence, problem, impact, and practical fix.
```

### 6. Loading states

Check loading feedback for pages, data fetching, submissions, uploads, searches, and long-running actions.

```text
Audit loading states. Find missing or unclear loading feedback.
For each issue: location, evidence, risk, current behavior, expected behavior,
and available next action.
```

### 7. Empty states

Check whether empty states explain why the area is empty and what to do next.

```text
Audit empty states. Find missing, unclear, or unhelpful empty states.
For each issue: location, evidence, current behavior, expected understanding,
and available next action.
```

### 8. Success and confirmation

Check feedback and next action after create, save, submit, update, delete, or completion.

```text
Audit success and confirmation states. Find missing or unclear feedback
and missing next actions. For each issue: location, evidence, current behavior,
expected behavior, and available next action.
```

### 9. Error and failure recovery

Check whether errors explain what happened, what to do next, whether retry is possible, and whether work is preserved.

```text
Audit error and failure recovery. Find vague, missing, or unhelpful errors.
For each issue: location, evidence, risk, current behavior, expected behavior,
and recovery action.
```

### 10. Destructive actions and undo

Check delete, remove, cancel, overwrite, publish, permanent changes, and unsaved changes.

```text
Audit destructive actions and undo. Find missing confirmations, unclear consequences,
missing undo, and accidental data-loss risks. For each issue: location, evidence,
risk, current behavior, expected behavior, and recovery action.
```

### 11. Visual consistency

Check hierarchy, button hierarchy, spacing, alignment, typography, repeated components, and inconsistent patterns.

```text
Audit visual consistency. Find inconsistent hierarchy, buttons, spacing,
typography, components, and patterns. For each issue: location, evidence,
inconsistency, impact, and fix. Prefer reusable-component fixes.
Do not change style unless it creates a usability problem.
```

### 12. Component and label consistency

Check whether the same action uses the same label and behavior across the scope.

```text
Audit component and label consistency. Find inconsistent labels, repeated components
behaving differently, and unclear or duplicated language. For each issue: location,
evidence, inconsistency, impact, and fix. Prefer reusable-component fixes.
```

### 13. Accessibility

Check keyboard navigation, visible focus, labels, helper text, contrast, readability, useful errors, screen-reader labels, and touch targets where relevant.

```text
Audit accessibility. Find keyboard, focus, label, contrast, readability,
error-message, screen-reader, and touch-target issues. For each issue: location,
evidence, problem, impact, and practical fix.
Do not claim compliance without verification.
```

### 14. Responsive / mobile

Check small-screen layout, touch targets, navigation, forms, tables, horizontal scrolling, and reachability of critical actions.

```text
Audit responsive and mobile experience. Find layout, navigation, form,
touch-target, scrolling, and content problems on small screens.
For each issue: location, evidence, problem, impact, and practical fix.
```

### 15. Simulated first-time user test

Run only if an interactive browser or app-testing tool is available.

Rules:

- Use only the visible interface.
- Do not inspect code, routes, database, DOM, or implementation details.
- Do not fix anything during the test.
- Record only issues that actually occur.
- Test relevant scenarios: new user, returning user, user in a rush, user with existing data, and small-screen user.

Use this test prompt:

```text
You are <persona>. Complete this task through the visible interface only:
<task and success criteria>.

Do not inspect code, routes, database, DOM, or implementation details.
Behave like a first-time user. Do not fix anything during the test.

Report whether the task completed, friction, wrong turns, hard-to-find actions,
unexpected behavior, missing feedback, uncertainty, and blockers.
For each important issue: what you tried, expected, happened, severity,
and recommended fix. Report only issues that occurred.
```

If no browser or app-testing tool is available, do not pretend to test. State that simulated testing was skipped and audit from available code, screenshots, routes, components, and user description instead.

## Step 5: Prioritized report

Run only if check 16 is selected.

Combine only selected-check findings into one prioritized backlog. Put foundational issues before cosmetic ones.

```md
# Enkay UX Audit Summary

## Scope
- Requested scope:
- Checks selected:
- Checks not run:

## Key findings
1. **P0/P1/P2/P3 — <issue>**
   - Evidence:
   - Why it matters:
   - Recommended fix:
   - Scope:

## Full findings
| Priority | Issue | Evidence | Why it matters | Recommended fix | Scope |
|---|---|---|---|---|---|

## Questions
- ...

## Next step
- Ask the user whether to fix selected P0/P1 issues.
```

## Edge cases

When relevant to the selected scope, check:

- First-time user with no data
- Returning user with lots of data
- Empty search results
- Slow loading or failed request
- Expired session or permission denied
- Invalid form input
- Duplicate submission
- Unsaved changes
- Mobile or narrow viewport
- Keyboard-only use
- Long labels, long names, or long error messages

Do not force every edge case into every audit. Include only cases relevant to the selected scope and checks.

## Whole-project passes

Run only if check 17 is selected.

Do not audit every file in one pass. Audit in passes:

1. Global navigation, layout, authentication, dashboard/home
2. Core create/edit/delete flows
3. Search, filters, lists, detail views
4. Settings, account, permissions, destructive actions
5. Error, loading, empty, and recovery states
6. Cross-cutting consistency and accessibility

Create and maintain an inventory:

| Area | Files or routes | Main user task | Status |
|---|---|---|---|
| Authentication | /login, /signup | Sign in or create account | Pending |
| Dashboard | /dashboard | Understand status and act | Pending |
| Core workflow | /projects, /projects/new | Create and manage work | Pending |
| Settings | /settings | Manage account/preferences | Pending |

Statuses: `Pending`, `In progress`, `Audited`, `Blocked`, `Out of scope`.

After each pass, present findings and ask which pass to run next.

## Implementation gate

Do not implement changes automatically.

1. Present findings and prioritized recommendations.
2. Ask which P0 and P1 issues to fix.
3. Propose the smallest set of approved changes.
4. If any approved fix touches UI, UI text, or UI consistency, choose the fix method (see "UI fix method" below).
5. Implement only approved changes.
6. Re-run the affected flow or task.
7. Confirm the original issue is resolved and no new friction was introduced.
8. If a fix cannot be verified, state what still needs manual testing.

## UI fix method

Run only when approved fixes involve UI, UI text (labels, errors, empty states, microcopy), or UI/visual/component consistency. Skip for logic-only or backend fixes.

1. Check whether the `impeccable` skill is installed: look for `impeccable` in the available skills list, or at `~/.claude/skills/impeccable`, `.claude/skills/impeccable`, or in an installed plugin.
2. **If installed**, ask:

```text
How should I fix the UI and check its consistency?

1. Use the Impeccable skill
2. Use Claude's default approach

Reply with 1 or 2.
```

3. **If not installed**, tell the user the Impeccable skill is not installed and ask them to install it first, then offer the same choice:

```text
The Impeccable skill is not installed. Install it for stronger UI, UI-text, and consistency fixes, then reply:

1. I installed it, use Impeccable
2. Skip it, use Claude's default approach
```

Do not install it yourself unless the user asks.

4. Apply the chosen method to the approved UI fixes only, including UI text and consistency checks across the affected screens.
5. Keep the same rules: approved changes only, minimal fixes, then re-run the affected flow (steps 6–8 above).

## Example finding

**P1 — Shipping cost is unclear before payment**

- Evidence: `/checkout/payment` shows “Continue to payment” before displaying shipping options or final total.
- Why it matters: Users may be surprised by the final amount and abandon checkout.
- Recommended fix: Show estimated shipping cost and updated total before payment, or clearly state that shipping is calculated on the next step.
- Scope: Checkout flow

## Guardrails

- Do not invent research, analytics, or user feedback.
- Do not claim accessibility compliance without verification.
- Do not make broad redesign recommendations from one screen.
- Do not run unselected checks.
- Do not implement changes before approval.