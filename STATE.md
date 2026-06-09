# Amazonia Floors 2.0 — Project State / Resume Guide

_Last updated: 2026-06-09. If picking this up fresh, read this first._

## What this is
Website 2.0 redesign Leone is **selling to a friend** (owner of Amazonia Floors, LLC — hardwood flooring, Baltimore/Harford County MD, 410-841-9780). Deal: **$999 total, $500 deposit already paid, $499 balance due.**

## Where everything lives (all durable / cloud-backed)
- **Local working dir:** `~/amazonia-floors-2.0/`
- **GitHub repo (backup + host):** `eterniteai/amazonia-floors-preview` (public). Redeploy = `git push` → GitHub Pages auto-rebuilds (~1 min).
- **LIVE URLs (served by GitHub — stay up even if Mac off):**
  - Site preview: https://eterniteai.github.io/amazonia-floors-preview/
  - **Signable proposal (friend has this):** https://eterniteai.github.io/amazonia-floors-preview/proposal.html
  - Pitch page: https://eterniteai.github.io/amazonia-floors-preview/pitch.html
- **Signature backend (Supabase, cloud):** project `amazonia-floors` ref `rmfsmrlddbjyyxjlqloy`. Table `public.proposal_signatures` (RLS: anon INSERT only). View signers: https://supabase.com/dashboard/project/rmfsmrlddbjyyxjlqloy/editor . Count RPC (no PII): `proposal_signature_count()`.
- **Local resume tools:** sign-watcher script `~/.hermes/scripts/amazonia-sign-watch.sh` + (unloaded) plist `~/Library/LaunchAgents/com.goddy.amazonia-sign-watch.plist`.

## Files
- `index.html` — full redesign (Soft-3D plank-"A" logo, photo service cards, Finished Work, FAQ, etc.). noindex + canonical→amazoniafloors.com (preview hygiene).
- `proposal.html` — online signable proposal (Atlas score card, revenue section, $999/$500/$499 pricing, sign→Supabase).
- `pitch.html` — pitch (PDF source).
- `privacy.html`, `terms.html`, `robots.txt`, `sitemap.xml`, `llms.txt`, `site.webmanifest`.
- `brand/` — logo SVG + PNGs (favicon, lockups, mark). `Atlas-Today-vs-After.png` — the scorecard graphic.
- `img/` — real client photos + 4 stock service images (vinyl/tile/carpet/commercial — REPLACE with real before launch).

## Atlas scores (measured this project)
- Current amazoniafloors.com: **56.7 (Bronze)** — real, measured.
- New build (preview host): **68.6 (Silver)** measured.
- Projected on his domain + 1st SEO package: **≈84 (Gold)**.
- ⚠️ **CONFIDENTIALITY LOCK:** never expose Atlas pillars/weights/checks in any client-facing artifact. Only headline score + tier + generic categories. See memory `lock_atlas_confidentiality.md`.

## Status
- ✅ Site + logo + proposal + pitch + Atlas card + revenue section — done & live.
- ✅ Pricing updated to $999 / $500 paid / $499 due (incl. sign agreement text).
- ✅ Git history scrubbed (squash+force-push). NOTE: 2 old leaked SHAs (70df658, 2196e51) still reachable by exact SHA until GitHub GC — guaranteed purge = delete+recreate repo (do AFTER friend signs).
- ⏳ Signatures: **0 so far.**

## Open / pending
1. **Sign notification watcher** — built, NOT running. Enable: `launchctl load ~/Library/LaunchAgents/com.goddy.amazonia-sign-watch.plist` (needs Leone OK / permission).
2. **Git-history full purge** — delete+recreate repo (same name keeps URL). Do after he signs.
3. **Before real launch:** swap 4 stock service photos for real jobs; replace placeholder stats (15yr/1,200 floors/5.0★) + testimonials; confirm `info@amazoniafloors.com` email + real street address (boosts Local SEO) + social handles.
4. Optional: swap calculator assumptions ($3,500 avg job / 40% close) for friend's real numbers.

## How to redeploy any change
`cd ~/amazonia-floors-2.0 && git add -A && git commit -m "..." && git push` → live in ~1 min. Always `grep` for pillar terms before committing (confidentiality lock).
