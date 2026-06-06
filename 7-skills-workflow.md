- skill 1: https://lobehub.com/skills/refoundai-lenny-skills-writing-prds
- skill 2: https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md
- skill 3: https://mcp.directory/skills/nextjs-developer
- skill 5: https://emilkowal.ski/skill
- skill 5: https://explainx.ai/skills/cursor/plugins/deslop
- skill 6: https://www.react.doctor/
- skill 7: Please check cursor

prompt1: Use the /writing-prds to help me create a lightweight, build-ready PRD for a small product called Money Snapshot.

Money Snapshot is a manual-first personal finance dashboard. It helps users understand their current month by tracking income, expenses, recurring bills, subscriptions, and savings goals in one place.

Users should be able to add data manually and also import transactions from a simple CSV file. We are intentionally not building bank integrations, invoice uploads, OCR, financial advice, tax logic, investment tracking, auth, or a complex backend.

ask me as many questions as needed


prompt 2: Use the /grill-with-docs skill to pressure-test this PRD before implementation.

Find unclear terms, missing decisions, and product assumptions that could lead to messy code. For each issue, ask me one question at a time and give your recommended answer first.

Focus especially on transactions, bills, subscriptions, recurring items, savings goals, monthly snapshots, and CSV import.

Keep the goal simple: make the PRD clearer and more implementation-ready.


prompt 3: Use the /nextjs-developer skill to build Money Snapshot from the @prd.md and @CONTEXT.md

Implement a focused Next.js App Router MVP with a dashboard, manual transaction entry, recurring bills/subscriptions, savings goals, and CSV import with preview.

Follow modern Next.js patterns: Server Components by default, Client Components only where needed, Server Actions for mutations, proper loading/error states, and a clean production build.


prompt 4: Use the /emil-design-eng skill to polish the Money Snapshot UI.

Improve the existing app so it feels more intentional, responsive, and product-quality. Focus on hierarchy, spacing, cards, forms, buttons, empty states, subtle motion, accessibility, and removing anything that feels generic or AI-generated.

Keep the product simple. Do not redesign it from scratch.

@prd.md @CONTEXT.md


prompt 5: Use the /deslop skill to clean up the current branch.

prompt 6: # React Doctor: money-snapshot

Score: 84/100

98 issues found

WARN no-react19-deprecated-apis (×24)

forwardRef is no longer needed on React 19+ — refs are regular props on function components; remove forwardRef and pass ref directly

- src/components/ui/card.tsx:4

- src/components/ui/dialog.tsx:13

- src/components/ui/alert-dialog.tsx:12

- +6 more files

ERROR server-auth-actions (×19)

Server action "updatePlannedIncome" — add auth check (auth(), getSession(), etc.) at the top

- src/app/actions.ts:19

WARN server-sequential-independent-await (×9)

Sequential `await` without a data dependency on the previous result — wrap the independent calls in `Promise.all([...])` so they race instead of waterfalling

- src/lib/month.ts:134

- src/app/settings/page.tsx:17

- src/lib/sample-data.ts:37

- +3 more files

WARN design-no-em-dash-in-jsx-text (×6)

Em dash (—) in JSX text reads as model output — replace with comma, colon, semicolon, or parentheses

- src/app/subscriptions/page.tsx:43

- src/app/settings/page.tsx:50

- src/components/csv-import-client.tsx:47

- +3 more files

WARN unused-export (×6)

Unused export: `monthKey`

- src/lib/format.ts:23

- src/lib/month.ts:19

WARN react-compiler-destructure-method (×5)

Destructure for clarity: `const { push } = useRouter()` then call `push(...)` directly — easier for React Compiler to memoize and clearer about which methods this component depends on

- src/components/month-picker.tsx:32

- src/components/onboarding-dialog.tsx:27

- src/components/settings-actions.tsx:56

- +1 more files

WARN async-await-in-loop (×5)

await inside a for…of loop runs the calls sequentially — for independent operations, collect them and use `await Promise.all(items.map(...))` to run them concurrently

- src/lib/month.ts:117

- src/lib/sample-data.ts:25

- src/app/actions.ts:102

WARN async-parallel (×4)

6 sequential await statements that appear independent — use Promise.all() for parallel execution

- src/lib/sample-data.ts:33

- src/app/actions.ts:138

WARN no-prevent-default (×3)

preventDefault() on <form> onSubmit — form won't work without JavaScript. Use a server action (`<form action={serverAction}>`) for progressive enhancement

- src/components/planned-income-form.tsx:22

- src/components/inline-crud-form.tsx:29

- src/components/expense-form.tsx:40

WARN prefer-tag-over-role (×3)

Prefer the semantic `<progress>` element over `role="progressbar"` on a generic tag.

- src/app/savings/page.tsx:83

- src/components/sample-banner.tsx:6

- src/app/page.tsx:254

+10 more rules

Full trace: /var/folders/65/3cf1q9xn251c3f_s5mxtbyn80000gn/T/react-doctor-48fba149-7665-4bcd-9e93-1e1a92a01942

## How to fix

1. Run `pnpm dlx react-doctor@latest --verbose` to see full details

2. Fix errors first, then warnings. Start with high-count rules.

3. Read the code before acting. Treat findings as hypotheses, not commands.

4. Fix root causes, not symptoms. Don't suppress rules without evidence.

5. Run `npx react-doctor@latest --verbose --diff` after changes to verify.

6. Split unrelated fixes into separate PRs.


prompt 7: Use the /thermo-nuclear-code-quality-review skill.

FIX EVERYTHING 
