# Makluman.com Advanced Salary Calculator

A standalone, responsive, bilingual (Bahasa Melayu / English) Malaysian salary-planning tool. Vanilla HTML/CSS/JS; no build step, framework, external font, analytics, API, cookie, or backend.

## Files
- `index.html` — complete calculator app (all CSS and JavaScript inline for simple static hosting).
- `wordpress-artikel-kalkulator-gaji.html` — article body to paste into a WordPress Custom HTML block. SEO title/meta/canonical remain managed by Rank Math/Yoast.
- `.nojekyll` — GitHub Pages compatibility marker.
- `.github/workflows/pages.yml` — deploys the root directory to GitHub Pages on pushes to `main`.

## Suggested repository
`bukitbesi/kalkulator-gaji` (create it first as a public repository; this environment cannot create a new GitHub repository directly).

## Deploy to GitHub Pages
1. Create a new **public** GitHub repository named `kalkulator-gaji` under `bukitbesi` (or your chosen owner). Do not add a README/license during repository creation if uploading these files as the first commit.
2. Upload `index.html`, `.nojekyll`, `README.md`, `.github/workflows/pages.yml` and optionally the WordPress article file. Commit to `main`.
3. In repository **Settings → Pages**, select **GitHub Actions** as the build/deployment source if it is not selected automatically.
4. Wait for the **Deploy static site to GitHub Pages** workflow to finish. Test the `https://<owner>.github.io/kalkulator-gaji/` URL.
5. Configure the desired subdomain DNS with your DNS provider. For `gaji.makluman.com`, add a CNAME record whose target is `<owner>.github.io` (replace `<owner>` with the actual GitHub account/organization). Do not include `https://` or a path in the CNAME target.
6. In **Settings → Pages → Custom domain**, enter `gaji.makluman.com`, save, wait for DNS verification, then enable **Enforce HTTPS** once available.
7. After the custom domain works, update the WordPress article's tool link if the final subdomain differs from `https://gaji.makluman.com/`.

## Calculator features
- BM/English toggle, responsive and keyboard-accessible form controls.
- Basic pay, recurring allowance, commission/other earnings, bonus, and OT estimate/manual OT.
- EPF/KWSP rate selector and manual override.
- SOCSO/PERKESO and EIS/SIP simplified estimate, manual amount, or not-applicable mode.
- Manual PCB entry (intentionally no invented tax engine).
- Other deductions and optional extra savings.
- Net monthly pay, annual net estimate, employer contribution/cost estimate, breakdown and simple budget allocation.
- Two-offer comparison by gross pay plus stated benefits.
- CSV export, print/save PDF, copy summary; no server-side processing.

## Important calculation limitations
- EPF percentage mode is a rough estimate; official contributions can depend on the statutory Third Schedule wage bands, category, and rounding. Use the manual amount from the payslip or official EPF source for a closer result.
- SOCSO/EIS automatic modes use simplified percentages capped at RM6,000, not the official contribution tables. These are clearly marked estimates. For exact values, choose manual mode and enter the payslip / official calculator result.
- PCB must be entered manually from the payslip or official e-PCB/MyTax calculation. This avoids fabricating a tax calculation without the complete official formula and personal tax details.
- OT is a planning estimate based on monthly basic salary / 26 / paid hours per workday × selected multiplier × OT hours. It is not a legal entitlement calculation.
- Employer EPF and employer cost are estimates only; change the rate for the employee category and confirm with payroll.
- The offer comparison is intentionally directional: it compares gross salary plus entered benefit value, not each offer's full net pay.

## QA / release checklist
- Test widths 320, 375, 768, 1024, and desktop.
- Verify both language modes, input recalculation, manual/estimate modes, reset, CSV, print, and copy summary.
- Verify values against official tables for any use that requires exact payroll output.
- Check GitHub Actions run, Pages URL, DNS CNAME, HTTPS, and final WordPress article link.
- No third-party scripts, remote fonts, images, or tracking are loaded by the calculator.

## Official references
- KWSP Third Schedule: https://www.kwsp.gov.my/en/epf-act-1991-third-schedule
- KWSP mandatory contributions: https://www.kwsp.gov.my/en/employer/responsibilities/mandatory-contribution
- PERKESO rates: https://www.perkeso.gov.my/en/rate-of-contribution
- PERKESO contribution calculator: https://perkeso.gov.my/en/our-services/employer-employee/contribution-calculator.html
- Malaysia Government PCB guide: https://www.malaysia.gov.my/my/topics/potongan-cukai-bulanan-pcb
- HASiL: https://www.hasil.gov.my/
