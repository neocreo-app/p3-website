# Verification: how you know it works

Learned the hard way across the Neocreo builds. The common failure is not a crash. It is a
**confident, plausible, wrong answer**: a push that "succeeded", a save that reported success, a
list that looks correctly empty, a page that "looks fine" on a laptop. In one day of Neocreo
builds, six such defects shipped past a fully passing test suite; every one appeared when a
person used the thing.

## The rules

1. **A push is not a deploy, and a deploy is not a working page.** After pushing, open the live
   site and look for the actual change. Vercel showing "Ready" is necessary, not sufficient. A
   changed file hash is not proof either; look for the content.
2. **Run the real build before pushing.** `npm run build` is what Vercel runs. Passing
   type-checks, passing tests, and a working dev server have all missed build failures before.
3. **Never run `npm run build` while `npm run dev` is running.** They share the `.next` folder and
   the build corrupts the dev server. Stop the dev server first; if it acts strange afterward,
   delete `.next` and restart it.
4. **An absence is not evidence.** "Empty", "missing", or "404" can mean the data never loaded or
   the request was refused, not that nothing exists. Check against something you know should
   show (a positive control on the same path).
5. **An error-free write can change nothing.** Databases with row-level security (Supabase) can
   accept a write and affect zero rows. Check that the thing actually changed.
6. **Test what the code really asks for.** A fake or mock that accepts any column name hides a
   wrong one. Run new database queries against the real dev database before pushing.
7. **Check phone width.** Most visitors arrive from a phone. Look at every changed page at about
   375px wide.
8. **Click the links you touched,** especially joins, applications, and anything that leaves the
   site.
9. **Caches lie.** Favicons, link previews (iMessage, Instagram, Slack), and redirects are cached.
   Test in a private window and expect previews to lag.
10. **Redirects are temporary unless truly final.** A permanent (308) redirect is cached by
    browsers forever and cannot be recalled. Default to temporary (307).
11. **A check is only proven when you have seen it fail.** Break the thing on purpose once and
    watch the check catch it.

## Before you say "done"

- [ ] Build passes (if the project has a `package.json`)
- [ ] The live site or preview URL shows the change
- [ ] Checked at phone width
- [ ] Links you touched go where they should
- [ ] Nothing secret or huge was committed

Then say plainly which of these you did and which you skipped.
