# Screenshot Capture Notes

Captured on **14 October 2026** from the public deployments using Playwright Core and Chrome 143.0.7499.193. These notes record the evidence behind the [portfolio README](../../README.md), not a security or production-readiness audit.

## Capture settings

- Desktop viewport: **1440 × 900 CSS pixels**, device scale factor **2**.
- Mobile viewport: **390 × 844 CSS pixels**, device scale factor **2**, mobile/touch emulation.
- Normal screenshots: **2880 × 1800** desktop and **780 × 1688** mobile pixels.
- YEENY category overview: the top **1440 × 590 CSS pixels** of the desktop viewport, saved at **2880 × 1180** pixels. This crop stops above the product grid with failing images.
- Viewport captures were used instead of full-page captures. The SkillMap roadmap is scrolled to the foundation and practice stages.
- Text, fonts, and relevant visible artwork were checked before accepting each screenshot. Loading-state and broken-image captures were rejected.
- WebP conversion used Pillow: quality 90 for YEENY photography; lossless for all SkillMap captures. No text, scores, controls, or images were replaced or retouched.
- The eight assets total **1,438,692 bytes** (approximately 1.37 MiB).

## Asset inventory

| File | Public page | State shown |
| --- | --- | --- |
| [YEENY desktop home](yeeny/desktop-home.webp) | `https://yeeny-v2.vercel.app/` | Promotion and collection hero; empty bag |
| [YEENY categories](yeeny/desktop-categories.webp) | `https://yeeny-v2.vercel.app/shop/` | Shop All heading and four category cards; cropped viewport |
| [YEENY mobile home](yeeny/mobile-home.webp) | `https://yeeny-v2.vercel.app/` | Mobile promotion, navigation, and collection hero |
| [SkillMap desktop home](skillmap/desktop-home.webp) | `https://talentbank-hackathon-yeeny.vercel.app/` | Education-to-opportunity introduction |
| [SkillMap career results](skillmap/desktop-career.webp) | `/candidate/results` on the SkillMap deployment | Built-in Aisyah sample: ranked results and roadmap preview |
| [SkillMap skill gaps](skillmap/desktop-skill-gap.webp) | `/candidate/skill-gap?career=solutions-consultant` | Selected career, skill coverage, missing-skill count, and priority gap |
| [SkillMap roadmap](skillmap/desktop-roadmap.webp) | `/candidate/roadmap?career=solutions-consultant` | Foundation and practice stages; no progress was marked complete |
| [SkillMap mobile home](skillmap/mobile-home.webp) | `https://talentbank-hackathon-yeeny.vercel.app/` | Mobile introduction, navigation, and calls to action |

## Reproducing the displayed states

Use a fresh browser profile with the viewport and scale settings above. Playwright was installed in a temporary tools directory; this documentation repository has no application dependencies or build step.

### YEENY

1. Open the homepage and wait for **New Collection**, the promotional text, fonts, and hero artwork to render. A network-idle wait can time out while the rendered application remains usable; wait for the actual content.
2. Capture the desktop and mobile homepages at the top of the page, with menus closed and the bag empty.
3. Follow **View All** to **Shop All**. Wait for the category cards and artwork to render.
4. Capture the top 590 CSS pixels for the category overview. Do not include failed product imagery or substitute an image source to make the storefront appear repaired.

### SkillMap

1. Capture the desktop and mobile landing pages in the default light appearance, with the navigation menu closed.
2. On desktop, select **Explore Pathway**, choose **Higher Education**, then **Continue**.
3. On **Profile Intake**, select **Use Sample** on the **Aisyah** card, then **Evaluate Career**. Use the site's supplied inputs unchanged.
4. Wait for **Your Best-Fit Career Pathways** on `/candidate/results`; capture the top of the page.
5. Follow **View Skill Gaps** on the Solutions Consultant result. Wait for **Skill Gap Breakdown** and capture the top of the page.
6. Follow **View Roadmap**, wait for **Your Career Trajectory**, then scroll until **Build evidence in sequence** is about 200 CSS pixels below the viewport top. Capture the foundation and practice tasks without changing progress.

The candidate pages depend on state generated through this flow. A fresh direct visit to a results URL does not reproduce the sample. No account login, private profile, authentication bypass, or injected application state was used.

## Verification and limitations

- Both deployment homepages returned **HTTP 200** and rendered in Chrome. The existing GitHub profile and portfolio repository links also returned **HTTP 200**.
- YEENY: followed catalog and product navigation; selected size M for Light Blue Dress and added it to the bag. The interface showed one item and a $100 subtotal. No checkout or payment was submitted.
- YEENY: the **Under $100** filter displayed three $60 products; **Name: A–Z** reordered the catalog; **Bags** displayed three bag products.
- YEENY: product-image optimizer requests returned **HTTP 502**, including a repeated request. The product detail image also failed. Those views were not accepted as portfolio screenshots. Hero and category artwork remained visible.
- SkillMap: secondary-school and higher-education landing previews were inspected; selecting Higher Education changed the preview content. These previews are illustrative, distinct from the evaluated sample screenshots.
- SkillMap: the public sample flow produced compatibility results and opened the selected career's skill-gap and roadmap pages. The sample was supplied by the application, not composed for the screenshots.
- Both landing pages had a document width of **390 CSS pixels** at the mobile viewport, with no horizontal overflow. Both mobile navigation menus opened. Captured desktop pages fit the **1440-pixel** viewport. This is browser emulation, not physical-device or full accessibility testing.
- Both applications serve Next.js assets and have React documented in the project notes. TypeScript, Tailwind, database, and authentication claims are attributed to the existing project documentation; this repository contains no application manifests or implementation source to audit.
- YEENY administration and payment processing, SkillMap employer/university account workflows, authorization, cloud persistence, and real-world career outcomes were not verified.
- Existing project READMEs were preserved. They contain broader plans, conditional setup examples, and unfinished placeholders. The YEENY notes also link to license/disclaimer files that are absent from this checkout; this change does not establish application licensing or repair those documents.
- No application source repository was supplied or verified. The portfolio Git remote is a documentation hub, not a source link for either deployed application.

Screenshots are dated evidence. Content, sample outputs, and deployment availability may change.
