# Big Turbo VR6 Build — timegan.ai

Single-file site. `index.html` is fully self-contained (fonts load from Google, everything else is inline). Checkboxes and photos save in each visitor's browser via localStorage.

## Deploy to timegan.ai (Cloudflare Pages + GitHub)

1. **Push to GitHub**
   - Create a repo (e.g. `vr6-build`).
   - Add `index.html` (and this README) at the repo root.
   - Commit + push to `main`.

2. **Connect Cloudflare Pages**
   - Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git.
   - Pick the repo. Build settings:
     - Framework preset: **None**
     - Build command: *(leave blank)*
     - Output directory: `/` (root)
   - Deploy. You'll get a `*.pages.dev` URL first.

3. **Point timegan.ai at it**
   - In the Pages project → Custom domains → Set up a custom domain → `timegan.ai`.
   - Since the domain is already on Cloudflare, DNS records are added automatically. Add `www` too if you want it.

4. **Updating the site**
   - Edit `index.html`, commit, push. Cloudflare redeploys automatically on every push to `main`.

## Notes
- Visitor checkbox/photo state is per-browser (localStorage). It is NOT shared or saved server-side — that would require the Next.js rebuild discussed separately.
