# Copilot Instructions for pneucalc

## Project Overview
This is a static web application for engineering calculations, primarily focused on pneumatics and mechanical components. The project consists of multiple HTML calculators, each serving a specific purpose (e.g., bearing selection, chemical compatibility, cutting speed, flange tables, etc.).

## Architecture & Structure
- **HTML Calculators:** Each calculator is a standalone HTML file in the root directory (e.g., `bearing_finder.html`, `chemcompat.html`).
- **Shared Data:** The `_data/modules.yml` file contains shared configuration or data modules used by calculators.
- **Includes & Layouts:**
  - `_includes/nav.html` provides navigation markup, likely included in each calculator for consistent site navigation.
  - `_layouts/default.html` is the main layout template for the site.
- **Assets:** All styles are in `assets/style.css`. No JavaScript assets are present by default; scripts may be inline within HTML files.

## Key Patterns & Conventions
- **No Build Step:** This project does not use a build system or bundler. All files are static and can be served directly.
- **Jekyll Compatibility:** The presence of `_data`, `_includes`, and `_layouts` suggests Jekyll or similar static site generator conventions. However, most calculators are pure HTML and do not require Jekyll-specific features unless templating is used.
- **Navigation:** Use `_includes/nav.html` for consistent navigation across calculators. Reference it via Jekyll `{% include nav.html %}` if templating is enabled.
- **Styling:** All custom styles should go in `assets/style.css`. Inline styles are discouraged unless necessary for calculator logic.
- **Data Access:** Shared data (e.g., modules) should be accessed from `_data/modules.yml` using Jekyll's data access patterns if templating is enabled.

## Developer Workflow
- **Editing Calculators:** Modify or add HTML files in the root directory for new calculators. Reuse navigation and layout includes for consistency.
- **Styling:** Update `assets/style.css` for global style changes.
- **Navigation:** Update `_includes/nav.html` to add new calculators to the site navigation.
- **No Tests/Builds:** There are no automated tests or build commands. All changes are manual and immediately reflected in the static files.

## Integration Points
- **Jekyll:** If using Jekyll, run `jekyll serve` to preview the site locally. Otherwise, open HTML files directly in a browser.
- **External Dependencies:** No external dependencies are present by default. If adding JavaScript libraries, include them via CDN in the relevant HTML files.

## Example: Adding a New Calculator
1. Create `newcalc.html` in the root directory.
2. Add `{% include nav.html %}` at the top for navigation (if using Jekyll).
3. Use the structure and styling conventions from existing calculators.
4. Update `_includes/nav.html` to link to the new calculator.

## Key Files
- `bearing_finder.html`, `chemcompat.html`, etc.: Individual calculators
- `_includes/nav.html`: Navigation markup
- `_layouts/default.html`: Main layout template
- `_data/modules.yml`: Shared data
- `assets/style.css`: Global styles

---

**For AI agents:**
- Always follow the file structure and reuse includes/layouts for consistency.
- Prefer editing existing calculators or creating new ones in the root directory.
- Reference shared data and navigation includes as appropriate.
- No build or test steps required; changes are live in static files.
