# Launch checklist: moving a site and going live

For moving a site off Wix or HubSpot CMS onto the standard stack, and for any first launch.

## Before cutover

1. **Inventory is complete.** Every old URL is in the outline, with "keep" or "redirect to".
   Wix and HubSpot both publish `sitemap.xml`; start there.
2. **Export what lives in the old platform:** form submissions, newsletter subscribers, contacts,
   images you own. Wix and HubSpot CMS keep nothing for you after you cancel.
3. **Forms tested on the preview URL:** submit each one; the contact lands in HubSpot with the
   right Brand value, and the notification email arrives.
4. **Meetings tested:** a test booking appears on the calendar.
5. **Redirects tested** on the preview: each old URL lands on the right new page.
6. **Copy passed** `/copy-pass`, and Paul (and Jas, for visuals) approved the preview.
7. **Legal pages are current:** privacy policy mentions HubSpot forms and tracking; dates are real.
8. **Write down the current DNS records** (a screenshot is fine) before changing anything.

## Cutover

1. Add the domain to the site's Vercel project.
2. Change **only** the website records (`A` / `CNAME` for the bare domain and `www`) to what
   Vercel shows. **Leave MX, SPF, DKIM, and DMARC exactly as they are**, or email breaks.
3. Wait for Vercel to show the domain as valid, with its certificate.
4. Open the live site in a private window: home, every page, every form, one redirect.

## After

1. Submit one real form on the live site and see it in HubSpot.
2. Send an email from that domain and check it still arrives (email records survived).
3. Submit the new `sitemap.xml` in Google Search Console.
4. **Only then** cancel the old platform: HubSpot CMS or Wix. Keep the HubSpot portal itself.
5. After 30 days: check form submits and bookings per page ([`README.md`](README.md), step 9).
