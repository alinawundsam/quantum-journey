# Quantum Journey — NFC Landing Pages

Two mobile landing pages for the IBM Innovation Studio Amsterdam quantum day.  
One static file, zero build step, zero tracking.

## Live URLs (after GitHub Pages is enabled)

| NFC Sticker | URL |
|---|---|
| Quantum Innovation | `https://<your-github-username>.github.io/quantum-journey/#innovation` |
| Quantum Safe | `https://<your-github-username>.github.io/quantum-journey/#safe` |

## How to update content

1. Open `index.html` and edit the `PAGES` / `EMAIL` / `COURSES` config block at the top of `<script>`.
2. `git add index.html && git commit -m "update content" && git push`
3. GitHub Pages re-deploys in ~30 seconds. The NFC tag URLs never change.

## How to swap the Innovation background photo

1. Export your photo as JPEG, compress to < 300 KB (e.g. tinyjpg.com), name it `bg-innovation.jpg`.
2. Drop it into `assets/bg-innovation.jpg` (overwrite).
3. Optionally add `assets/bg-innovation.webp` for browsers that support it (then update the CSS `background:` in `.bg-innovation` to use `image-set()`).
4. Commit and push.

## File structure

```
index.html          ← entire app (edit content here)
assets/
  avatar.png        ← IBM Innovation Studio avatar (round, 192×192)
  bg-innovation.jpg ← Innovation page background photo (full-viewport cover)
  grain.png         ← film-grain overlay texture
README.md
```

## Open placeholders

| Item | Location in index.html | What to fill in |
|---|---|---|
| Innovation explainer video | `PAGES.innovation.watch` | YouTube / IBM video URL |
| Innovation podcast episode | `PAGES.innovation.listen` | Spotify / podcast URL |
| Innovation reading material | `PAGES.innovation.read` | IBM article / report URL |
| Quantum Safe explainer video | `PAGES.safe.watch` | YouTube / IBM video URL |
| Quantum Safe podcast episode | `PAGES.safe.listen` | Spotify / podcast URL |
| Quantum Safe reading material | `PAGES.safe.read` | Already set to ibm.com/quantum/quantum-safe — confirm or replace |
| Innovation Studio inbox | `EMAIL` constant | Replace `alina.wundsam@ibm.com` if there's a shared inbox |
| Real Innovation background | `assets/bg-innovation.jpg` | Replace stand-in chandelier photo with the real event photo |
| WebP background variant | CSS `.bg-innovation` | Add `assets/bg-innovation.webp` + `image-set()` when you have a WebP encoder |
| OG image | `<meta property="og:image">` | Replace `assets/avatar.png` with a proper 1200×630 social preview image |
| Microsoft Forms prefill | `?source=innovation` / `?source=safe` | Verify the form accepts `source` as a prefill param; remove suffix if not |
