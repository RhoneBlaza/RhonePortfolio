# PROMPT_LOG.md

**Project:** Rhone Blaza — Portfolio Site (System Integration)
**Stack:** Laravel + Blade + Tailwind CSS

A log of prompts used during development, along with the resulting output for each task.

---

## 1. Smooth Scroll Navigation + Active Nav Highlighting

**Task:** Make the scroll animation smoother and highlight the active navigation bar.

**Prompt used:**
> In the hero section, make "Get In Touch" smoothly scroll to the `#contact` section and "View Projects" smoothly scroll to the `#projects` section (use `scroll-behavior: smooth` or JS `scrollIntoView({behavior: 'smooth'})`). Make sure every top-nav link (About, Education, Projects, GitHub, Contact) points to a matching section id and highlights as "active" when that section is in view.

**Result/Output:**
Generated the smooth scrolling and active navigation features successfully. No major follow-up was needed, as the existing JavaScript and CSS implementation already handled the required behavior.

---

## 2. Dark/Light Mode Toggle

**Task:** Make a dark and light toggle button that replicates the sun & moon, with OS preference detection for the color scheme.

**Prompt used:**
> Add a dark mode toggle:
> 1. Set `darkMode: 'class'` in `tailwind.config.js`.
> 2. Add a sun/moon icon toggle button in the navbar (desktop + mobile menu).
> 3. Clicking it toggles the `dark` class on the `<html>` element.
> 4. Persist the choice in localStorage (key: `"theme"`) so it survives reloads.
> 5. On first load, check localStorage; if empty, fall back to the OS preference via `window.matchMedia('(prefers-color-scheme: dark)')`.
> 6. Add `dark:` variants across every section with enough contrast to stay readable.
> 7. Add `transition-colors duration-300` on body/cards so the switch isn't jarring.
> 8. Implement with a tiny inline script in the Blade layout (no framework needed) so it runs before paint and avoids a flash of the wrong theme.

**Result/Output:**
Generated the dark mode system with full theme switching, persistence, and responsive support. The implementation includes a desktop/mobile sun-and-moon toggle, OS preference detection, localStorage persistence, complete `dark:` styling across the interface, smooth color transitions, and a mobile menu that closes automatically after selecting a link.

---

## 3. Skills Section

**Task:** Add a Skills section, placed between About and Education (and added to the nav bar).

**Prompt used:**
> Add a dedicated "Skills" section to my Laravel + Blade portfolio site, placed between About and Education (and added to the nav bar). Group skills into categories: Languages, Frameworks & Libraries, Databases, and Tools. Use the same dark theme, purple/violet accent colors, and card/badge styling already used elsewhere on the site (e.g. the tag pills on the Projects page). Each skill can be a small badge with an icon if a matching icon is available (devicon or simple-icons via CDN), otherwise just styled text. Make the section data-driven — pull the skill list from a config array or blade component prop, not hardcoded HTML, so I can update it easily later. Ask me for my actual skill list before finalizing content.

**Result/Output:**
Generated the skills section successfully, with the skill data managed in `PortfolioController.php` and displayed dynamically through the Blade view. Devicon icons were added for supported technologies, while SQL and Blade use styled text. The implementation was also verified with Pint formatting, passing tests, and a successful 200 route response.

---

## 4. Education Section Restructure

**Task:** Group Education entries into Formal Education (degree and senior high school) and Certifications, sorted newest first, with a visual divider between groups.

**Prompt used:**
> In the Education section of my Laravel + Blade portfolio, restructure the layout into two clearly labeled groups: "Formal Education" (degree program and senior high school) and "Certifications" (e.g. TESDA). Within each group, sort entries by date, most recent first. Keep the existing card style but consider a small visual distinction between the two groups (e.g. a different accent icon or a subheading divider).

**Result/Output:**
Generated the formal and certification sections with dynamic grouping and sorting. Each entry now includes its type and start year, allowing the controller to organize records by the latest year first and display them in separate styled groups. The Blade view adds gradient dividers for each group while preserving the existing card design and using appropriate icons. Pint formatting and all tests also pass successfully.

---

## 5. README.md

**Task:** Make a README.md file that briefly describes the project.

**Prompt used:**
> Include a basic README.md file describing your project (including project description)

**Result/Output:**
Replaced the default Laravel README with one describing the project: Rhone Blaza's personal portfolio built with Laravel, Blade, and Tailwind CSS, covering features, requirements, install/setup steps, and testing.
