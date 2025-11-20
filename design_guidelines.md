# STEPS UP Investment Management System - Design Guidelines

## Design Approach

**Selected Framework:** Material Design with modern fintech dashboard influences (Linear, Stripe Dashboard, Robinhood)

**Core Principles:**
- Data clarity and hierarchy above visual flourish
- Professional, trustworthy interface for financial operations
- Scannable information architecture for quick decision-making
- Consistent patterns across admin and investor portals

---

## Typography System

**Font Family:** Inter (Google Fonts) for UI, Manrope for headings
```
Headings: Manrope (600-700 weight)
- H1: 2.5rem (40px) - Page titles
- H2: 2rem (32px) - Section headers
- H3: 1.5rem (24px) - Card titles, widget headers
- H4: 1.25rem (20px) - Subsections

Body Text: Inter (400-500 weight)
- Base: 1rem (16px) - Standard text
- Small: 0.875rem (14px) - Secondary info, labels
- Tiny: 0.75rem (12px) - Table metadata, timestamps

Data Display: Inter Medium (500-600 weight)
- Large numbers: 2rem-3rem for key metrics
- Table data: 0.875rem for density
- Currency: Tabular numbers enabled
```

---

## Layout & Spacing System

**Tailwind Spacing Units:** 2, 4, 6, 8, 12, 16, 24

**Core Patterns:**
- Card padding: `p-6` (24px)
- Section spacing: `space-y-8` (32px between major sections)
- Component gaps: `gap-4` (16px between related items)
- Page margins: `px-6 md:px-8` responsive
- Content max-width: `max-w-7xl` for wide dashboards

**Grid Systems:**
- Dashboard: 3-column grid on desktop (`grid-cols-1 md:grid-cols-2 lg:grid-cols-3`)
- Tables: Full-width with horizontal scroll on mobile
- Forms: 2-column layout on desktop (`grid-cols-1 md:grid-cols-2`)
- Stat cards: 4-column on wide screens (`lg:grid-cols-4`)

---

## Navigation Architecture

**Admin Dashboard:**
- Persistent sidebar navigation (collapsible on mobile)
- Width: 240px desktop, overlay drawer on mobile
- Top bar with user profile, notifications, quick actions
- Breadcrumb navigation for deep pages

**Investor Portal:**
- Horizontal tab navigation for main sections
- Floating action button for primary actions (new investment)
- Bottom navigation on mobile for key areas

**Sidebar Structure:**
```
Dashboard (chart icon)
Investors (users icon)
Investments (trending-up icon)
VIP Codes (tag icon)
Binary Network (git-branch icon)
Commissions (dollar-sign icon)
Reports (bar-chart icon)
Settings (settings icon)
```

---

## Component Library

### Dashboard Widgets
**Stat Cards:**
- Compact metric display: Icon, label, value, trend indicator
- Grid layout: 4 cards across desktop
- Height: Auto-fit content, minimum 120px
- Include sparkline charts for trends

**Charts:**
- Line charts for investment growth over time
- Pie charts for portfolio distribution
- Bar charts for commission breakdowns
- Height: 300px-400px for main charts, 200px for secondary

### Data Tables
**Structure:**
- Sticky header row
- Alternating row hover states
- Action column (right-aligned) with icon buttons
- Pagination footer: 10/25/50 rows per page
- Search and filter controls above table
- Responsive: Card-style rows on mobile (stack columns vertically)

**Column Patterns:**
- ID columns: Monospace font, 80px width
- Date columns: 120px width
- Status badges: Inline, pill-shaped
- Currency: Right-aligned, bold weight

### Forms
**Input Fields:**
- Floating labels on focus
- Helper text below inputs
- Error states with inline messages
- Grouped related fields with `space-y-4`

**Form Layouts:**
- Two-column responsive grid for efficiency
- Full-width for text areas and complex inputs
- Action buttons: Right-aligned, primary + secondary pattern

### Binary Tree Visualization
**Interactive Tree:**
- Hierarchical node layout using org-chart pattern
- Node cards: 160px width, avatar + name + stats
- Connecting lines between nodes
- Zoom controls for large networks
- Expandable/collapsible branches
- Highlight path on hover

### Status Indicators
**Badges:**
- Active: Subtle success treatment
- Pending: Warning treatment
- Inactive: Muted gray
- Completed: Success green accent
- Pills with 2px padding, rounded-full

### Investment Cards (Investor Portal)
**Card Structure:**
- Plan name header with tier badge
- Large currency display for amount
- Progress bar for maturity timeline
- Return metrics (expected vs. actual)
- Quick actions footer

---

## Page-Specific Layouts

### Admin Dashboard (Home)
```
[Top Stats Row: 4 metric cards]
[Middle Section: 2-column grid]
  - Left: Investment growth chart
  - Right: Recent activity feed
[Bottom Section: 2-column grid]
  - Left: Top investors table
  - Right: Commission summary
```

### Investor Management
- Filter bar: Search, status dropdown, date range
- Data table with actions: View, Edit, Delete
- Bulk actions toolbar when rows selected

### Binary Network
- Full-width tree visualization
- Side panel with selected investor details
- Controls: Search, zoom, filter by level

### Investor Portal Dashboard
```
[Welcome Header with account summary]
[3-Column Metrics: Total Invested, Returns, Commissions]
[Active Investments Grid: Card layout]
[Referral Network Preview]
[Recent Transactions Table]
```

---

## Responsive Breakpoints
- Mobile: < 768px (single column, stacked cards)
- Tablet: 768px - 1024px (2-column grids)
- Desktop: > 1024px (full multi-column layouts)

---

## Accessibility
- All form inputs have visible labels
- Focus indicators on interactive elements
- Sufficient contrast for all text
- Keyboard navigation support
- ARIA labels for icon-only buttons

---

## Images
**No hero images** - This is a data-focused dashboard application, not a marketing site.

**Profile Avatars:**
- Investor profile pictures in tables and detail views
- Circular, 40px in lists, 80px in headers
- Fallback: Initials on colored background

**Icons:**
- Use **Heroicons** (outline style) consistently throughout
- 20px-24px for UI elements, 32px for stat cards

---

## Animation Guidelines
**Minimal, purposeful animations only:**
- Page transitions: Fade-in on route change (200ms)
- Loading states: Skeleton screens, no spinners
- Data updates: Subtle highlight flash on change
- No scroll-triggered or decorative animations