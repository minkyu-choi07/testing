Here's the prompt:

---

**Prompt:**

> In the ChaMP Next.js 14 codebase (`champ-web/`), implement a **persistent top navigation with tabbed Resources section** so that navigation tabs are always visible — even when viewing individual resource content like a demo or blog post.
>
> **Requirements:**
>
> **1. Sticky Tab Bar Below Navbar**
> - Add a secondary tab bar directly below the existing `Navbar` component
> - It should be `position: sticky` (or fixed) so it stays visible on scroll, sitting right below the main nav
> - Tabs: `Overview` | `Demos` | `Blog` (extend as needed)
> - `Overview` = the main product page (current homepage content)
> - `Demos` = grid of demo cards
> - `Blog` = grid of blog post cards
> - Active tab gets an underline in `var(--clr-accent)` — inactive tabs use `var(--clr-text-dim)`
> - Tab bar styled with `var(--clr-surface)` background, `border-b border-[var(--clr-border)]`, `font-mono`, uppercase, small text tracking-wide
>
> **2. Tab Navigation Behavior**
> - Clicking a tab shows that tab's content **below the tab bar** without a full page navigation — use client-side state or nested layout routing
> - Two approaches (pick the cleanest for App Router):
>   - **Option A — Layout route groups:** Use `src/app/(site)/layout.tsx` with the tab bar, and nested routes like `/(site)/page.tsx` (Overview), `/(site)/demos/page.tsx`, `/(site)/blog/page.tsx`, `/(site)/demos/[slug]/page.tsx`
>   - **Option B — Client-side tabs:** Single page with a `"use client"` tab switcher component that conditionally renders content panels
> - **Option A is preferred** because it supports direct linking (`/demos/coa-generation`) and browser back/forward
>
> **3. When Viewing a Single Resource (e.g. `/demos/[slug]`)**
> - The Navbar + Tab Bar remain visible and functional at the top
> - The `Demos` tab should appear active
> - User can click any other tab to navigate away
> - The demo content renders below the tab bar inside a `glow-card corner-marks` container
> - Back link above the content: `← Back to Demos` styled in `font-mono`, `var(--clr-accent)`
>
> **4. Styling Rules (from FRONTEND.md)**
> - No border-radius on the tab bar or tab buttons
> - Active tab: `var(--clr-accent)` text + 2px bottom border in `var(--clr-accent)`
> - Inactive tab: `var(--clr-text-dim)` text, no bottom border, hover brightens to `var(--clr-text)`
> - Tab bar font: `var(--font-mono)`, `0.75rem`, `uppercase`, `tracking-wide`
> - Tab bar background: `var(--clr-surface)` with `border-b border-[var(--clr-border)]`
> - Tab bar should have `z-40` (Navbar is `z-50`) so it layers correctly
> - Transition on tab switches: subtle fade or instant — no heavy animations
>
> **5. Integration**
> - Move the existing homepage sections (Stats, Problem, Architecture, Capabilities, Results, Team) under the `Overview` tab
> - Hero section stays **above** the tab bar (it's the landing intro, not tab content)
> - Footer stays **below** all tab content on every tab
> - Update `Navbar` links to point to the correct tab routes instead of anchor `#` links

---

This gives your agent the full spec — routing strategy, styling rules, layout behavior, and how it integrates with the existing components. Want me to adjust anything?
