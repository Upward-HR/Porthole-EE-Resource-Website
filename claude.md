# Porthole Hospitality — Employee Portal

## Project Overview

A static, single-file HTML employee resource portal for **Porthole Hospitality**, a restaurant located at 20 Custom House Wharf, Portland, ME 04101. The portal serves as an internal-only landing page for new and existing employees, centralizing access to key documents, HR contacts, and operational reminders.

The entire project lives in one file: `porthole-employee-portal.html`. There is no build system, no JavaScript framework, and no backend — just vanilla HTML and CSS.

## Purpose & Audience

- **Audience:** Restaurant employees (new hires and existing staff)
- **Use case:** Onboarding hub — links to the company handbook, HR documents, benefits guide, emergency procedures, and workplace injury protocols
- **Access:** Internal use only; not a public-facing page

## Architecture

Single-file static HTML with embedded CSS. No JavaScript. No external dependencies except two Google Fonts loaded via CDN:
- `Playfair Display` (serif, used for headings)
- `Source Sans 3` (sans-serif, used for body text)

### Layout Structure (top to bottom)

1. **Header** — Navy bar with color stripe, logo circle, "Porthole Hospitality / Employee Resource Center" title, and "Team Portal" badge
2. **Hero Band** — Red announcement bar with HR contact reminder
3. **Notice Box** — Yellow-tinted alert for new employee onboarding steps
4. **Core Documents** section — Card grid with links to:
   - Company Handbook (Google Doc)
   - Welcome Letter (Coming Soon)
   - HR Information (Google Doc + direct email)
   - Benefits Guide (PDF + EAP phone number)
   - Emergency Action Plan (link placeholder)
   - Workplace Injury Protocol (link placeholders)
5. **Key Contacts** strip — HR email, owner email, restaurant phone, EAP hotline
6. **Quick Reminders** section — Pay schedule, time-off process, work schedules, employee discounts
7. **Footer** — Address and internal-use notice

## Design System

All colors are defined as CSS custom properties on `:root`:

| Variable       | Value     | Usage                        |
|----------------|-----------|------------------------------|
| `--red`        | `#C8242B` | Primary accent, card tops, labels |
| `--blue`       | `#4AAFC8` | Secondary accent, header stripe   |
| `--navy`       | `#1B3A5C` | Background, text, card tops       |
| `--cream`      | `#F8F4EE` | Page background, link item bg     |
| `--white`      | `#FFFFFF` | Card backgrounds                  |
| `--light-blue` | `#E8F5FA` | Blue icon backgrounds             |
| `--border`     | `#D9D0C4` | Card and section borders          |

**Typography:**
- Headings: `Playfair Display` (700/900 weight)
- Body/UI: `Source Sans 3` (300/400/600 weight)

**Card accent colors** use `.red`, `.blue`, or `.navy` classes on `.card-accent` div.

## Key Contacts (embedded in the page)

- **HR:** HR@upmgt.org
- **Owner/Management:** johnpjabar@gmail.com
- **Restaurant phone:** (207) 773-4653
- **EAP — NexGen:** 1-800-960-5371 · ID: PAS220

## Placeholder / Incomplete Items

Several document links are stubs that need real URLs added:
- Welcome Letter — New Employee
- Emergency Action Plan — 2026
- Injury & Incident Report Form
- Workers' Compensation Info

These are marked with `<span class="link-badge gdrive">Add Link</span>` or `"Coming Soon"` badges. When adding links, replace `href="#"` with the real URL and update the badge label (`gdoc`, `pdf`, or `gdrive`).

## Operational Notes

- **Pay period:** Mon–Sun, paid each Friday via direct deposit
- **Schedule posting:** Every Thursday for the following week
- **Time-off requests:** Email both `johnpjabar@gmail.com` and `HR@upmgt.org`; 4-week minimum notice for non-urgent leave
- **Employee discount:** 50% off food (excludes alcohol, kids meals, already-discounted items)

## Common Tasks

**Adding or updating a document link:**
Find the relevant card by its `<h2>` title. Update the `href` attribute on the `<a class="doc-link">` element. Change the `<span class="link-badge">` text and class (`gdoc`, `pdf`, or `gdrive`) to match the file type.

**Changing contact information:**
Update both the `.contact-strip` section near the bottom AND any inline references in the hero band or notice box, as contact info appears in multiple places.

**Adding a new card:**
Copy an existing `<div class="card">` block. Choose an accent color class (`red`, `blue`, or `navy`) and matching icon background class (`red-bg`, `blue-bg`, or `navy-bg`). Place it inside the appropriate `.card-grid`.

**Changing branding colors:**
Edit the CSS custom properties in the `:root` block at the top of the `<style>` tag. All color references use these variables, so changes propagate automatically.
