# LHE2LAX Website Redesign (lhe2lax-website)

This repository holds the code for the official LHE2LAX website, designed in October 2025. It is built as a minimalist, three-page static site with custom color variables and animation (Rotating Banner) for fast performance and easy maintenance.

---

## 1. Project Structure

* **index.html:** Home Page (includes Rotating Swiper Banner).
* **about.html:** About Page (includes Split-Screen Image/Text layout).
* **blog.html:** Blog/Insights Page.
* **css/style.css:** Contains all custom color variables and styling overrides.
* **images/:** Contains all required images (`about-team.png`, `tip-cloud.png`, etc.).

---

## 2. Deployment Workflow & Environments

The project is hosted on Render and uses a standard Git Flow model for safe updates.

| Environment | Render Service Name | Git Branch | Purpose |
| :--- | :--- | :--- | :--- |
| **Production (LIVE)** | `lhe2lax-prod-2025` | `main` | Handles `www.lhe2lax.com`. Only accepts code merged from `develop` after testing. |
| **Staging (TESTING)** | `lhe2lax-staging` | `develop` | Deploys automatically upon every push to the `develop` branch. Used for live testing/previewing before Production merge. |

---

## 3. Key Design & Technical Notes

### A. Color Palette (Defined in `css/style.css :root`)

| Variable | Color (Hex Code) | Usage |
| :--- | :--- | :--- |
| `--bs-primary` | `#2c3e50` (Charcoal Gray) | Main header background and H3/H5 text. |
| `--bs-logo-color` | `#EA4335` (Vibrant Orange) | Navigation bar logo. |
| `--bs-accent-color` | `#548809` (Deep Lime) | H2 headings (Pillar & Blog Headings). |
| `--bs-blue-accent` | `#0d6efd` (Default Blue) | Rotating Banner H3 text (for contrast). |
| `--bs-light-cta` | `#f0f7f4` (Soft Cream) | Background color for all CTA blocks. |
| `--bs-text-dark-gray`| `#444444` (Dark Gray) | Standard Body Text (Paragraphs and List Items). |

### B. Technical Specifications

* **Rotating Banner:** Uses **Swiper.js** with `delay: 4000` and responsive breakpoints (`slidesPerView: 1` mobile, `slidesPerView: 3` desktop).
* **File Naming:** All HTML/CSS/Image filenames **must be entirely lowercase and use hyphens** to prevent case-sensitivity errors on the Render server.
* **CSS Specificity:** Custom variables are applied with `!important` or specific element targeting (like `h2` and `p`) to ensure consistency over Bootstrap defaults.

---

## 4. How to Update Content (Standard Workflow)

1.  Ensure you are on the **`develop`** branch (in GitHub Desktop).
2.  Make changes/add images locally.
3.  Commit your changes locally.
4.  Push the changes to GitHub (`git push origin develop`).
5.  **Test the Staging URL** (`lhe2lax-staging` on Render).
6.  If approved, merge `develop` into `main` to trigger the Production deployment.